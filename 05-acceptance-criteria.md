# Tournament Management System — Product Document Pack

## 5. Acceptance Criteria

### A. Tournament creation

AC-1: [MVP] Create tournament draft

Given I am an admin, when I create a tournament, then it is saved as a private draft even if required basic tournament information is incomplete. Required basic tournament information is a tournament name, description, game system or activity, start date, and rules summary.

AC-2: [MVP] Required fields  
Given I am creating or editing a draft, when any required basic tournament information is missing or no MVP format is selected, then I cannot publish or start the tournament until it is completed or selected. Format-specific setup and other start requirements remain governed by AC-3, AC-21, and AC-22.

AC-3: [MVP] Format selection  
Given I am creating a tournament, when I select single elimination, round robin, or Swiss, then the system shows the setup options and eligible participant range required for that format before start; Swiss also requires the admin to select its round count.

AC-4: [MVP] Publish public tournament

Given a valid draft, when the admin publishes it as registration open or registration closed, then its public page becomes visible; the draft is visible only to its admin before publication.

### B. Joining

AC-5: [MVP] Open joining  
Given joining is open for a public tournament, when a participant submits the required MVP join information, then they are added with joined status during registration open or pending-placement status during in-progress play.

MVP joining requires only a display name. Faction and faction-specific rules text are optional participant details managed by an admin.

AC-6: [MVP] Joining closed  
Given a tournament is in registration closed, when a participant visits its public page, then they cannot join and must see the joining status.

AC-7: [Later Scope] Custom fields  
Given the admin requires custom registration fields, when a participant registers, then the participant must complete those fields before registration is accepted.

AC-8: [Later Scope] Registration limit and waitlist  
Given registration limits or waitlists are supported, when the participant limit is reached, then new registrations are blocked or waitlisted according to defined admin settings.

### C. Participant management

AC-9: [MVP] Manual add  
Given I am an admin, when I add a participant by display name, then the participant appears in the participant list.

AC-10: [MVP] Bulk add  
Given I am an admin, when I paste multiple participant names, then the system creates separate participant entries.

AC-11: [MVP] Edit participant details
Given the tournament has not started, when the admin edits a participant display name or other participant details, then the update appears in the bracket preview and participant list. Given a tournament is not cancelled, when an admin edits a participant's faction or faction-specific rules text, then the update is saved without changing seeds, pairings, scores, standings, placements, or completed match history; this is allowed before, during, and after competition.

AC-12: [MVP] Controlled after-start placement

Given a tournament is in progress and an entrant is pending placement, when the admin selects a placement, then the system shows the affected unfinished pairings and standings and requires confirmation before applying the change; completed match history is unchanged.

AC-13: [MVP] Remove participant before start  
Given the tournament has not started, when the admin removes a participant, then the participant is excluded from the bracket preview or scheduled pairings.

AC-14: [MVP] Participant withdrawal before start  
Given the tournament has not started, when a participant withdraws from a tournament they joined, then they are shown as withdrawn and excluded from the bracket preview or scheduled pairings.

### D. Check-in

AC-15: [Later Scope] Enable check-in  
Given check-in is supported and enabled, when check-in opens, then registered participants can mark themselves as present.

AC-16: [Later Scope] Checked-in list  
Given check-in is active, when the admin views participants, then checked-in and not-checked-in participants are clearly separated.

AC-17: [Later Scope] Start with checked-in participants  
Given check-in is required, when the admin starts the tournament, then the admin must confirm how unchecked participants are handled.

### E. Seeding and bracket preview

AC-18: [MVP] Manual seeding  
Given participants exist before start, when the admin changes seed order, then the admin-only bracket preview or scheduled pairings regenerate automatically according to the selected format's seed rules.

AC-19: [MVP] Shuffle seeding  
Given participants exist before start, when the admin shuffles seeds, then participant order changes and the system automatically regenerates the admin-only preview before starting.

AC-20: [MVP] Final bracket lock  
Given the tournament starts, when the final bracket or scheduled pairings are generated, then viewers can distinguish them from earlier previews; format, structure, outcome scoring, standings points, tiebreakers, seeds, and bracket or schedule rules are locked.

### F. Tournament start

AC-21: [MVP] Start tournament  
Given registration is closed and required setup is complete, when the admin starts the tournament, then the final bracket or schedule is created, the tournament enters in progress, and first-round matches become active.

AC-22: [MVP] Prevent invalid start  
Given registration is open, required setup is incomplete, seeding is invalid, the selected format lacks enough active participants, or its participant count exceeds the MVP format limit, when the admin attempts to start the tournament, then the system prevents the start and explains what must be fixed.

### G. Match operations

AC-23: [MVP] Match page  
Given a match exists, when an admin, participant, or spectator views it, then they can see participants, score status, bracket or standings context, and its not-ready, active, or completed state. Table assignment, missions, scenarios, deployment maps, and round packets are not MVP match fields.

AC-24: [MVP] Match state visibility  
Given match states change during the MVP flow, when admins, participants, or spectators view the tournament, then they can see whether each match is not ready, active, or completed.

AC-25: [MVP] Round activation

Given a future round's prerequisites are complete, when an admin starts that round, then its not-ready matches become active and only assigned participants or admins can report their results; for Swiss, the next round is created only after every match in the preceding round is complete. MVP rounds have no scheduled start or end time, timer, or late-arrival handling.

AC-26: [MVP] Match context and upcoming visibility

Given a match exists or a participant has a future match generated by the bracket or schedule, when they view the tournament, then they can understand its progression position and see its opponent or pending source.

### H. Score reporting

AC-27: [MVP] Direct score reporting

Given a match is active, when an assigned participant or admin enters a valid format result, then the system saves it, completes the match, advances the winner when applicable, and updates standings. A valid result is a win or loss for single elimination, and a win, loss, or draw for round robin and Swiss.

AC-28: [MVP] Invalid score  
Given a result is missing, has no winner for single elimination, or records a draw for single elimination, when an assigned participant or admin submits it, then the result is rejected with a clear explanation and the match remains active. Game-specific numeric scores are not MVP result fields.

AC-29: [MVP] Participant self-reporting

Given an assigned participant submits a valid result for an active match, when it is saved, then it is final immediately without a confirmation or review state, subject only to the admin completed-match correction flow in AC-46.

AC-30: [Later Scope] Match proof  
Given proof is supported and required, when a score is submitted without proof, then the score cannot be finalized.

AC-31: [Later Scope] Disputed score  
Given disputes are supported and submitted scores conflict or are challenged, when a dispute is opened, then the match enters review status and does not advance until an admin resolves it.

AC-32: [Later Scope] Forfeit  
Given forfeits are supported, when the admin marks a forfeit, then the opponent advances or receives the defined result.

### I. Standings and tiebreakers

AC-33: [MVP] Standings update  
Given a valid match result is saved or an admin corrects a completed result, when standings are displayed, then wins, losses, ties, match points, and rank reflect that result in the same operation; a win is worth 3 match points, a draw is worth 1, and a loss is worth 0.

AC-34: [MVP] Tiebreakers  
Given participants are tied and the admin has selected one or more ordered tiebreakers before start, when standings are calculated, then the system applies match wins, Buchholz, or head-to-head in the selected order. If selected tiebreakers do not separate final standings, the participants share the placement.

AC-35: [MVP] Tiebreaker visibility  
Given tiebreakers affect ranking, when admins, participants, or spectators view standings, then the configured order, applied values, and explanation are visible; opponent win percentage, victory-point differential, and other game-specific tiebreakers are not available in MVP.

### J. Two-stage tournaments

AC-36: [Later Scope] Group creation  
Given two-stage tournaments are supported and selected, when the admin creates groups, then each participant is assigned to one group.

AC-37: [Later Scope] Automatic group assignment  
Given automatic group assignment is supported and selected, when groups are generated, then participants are distributed across groups for admin review.

AC-38: [Later Scope] Manual group assignment  
Given manual group assignment is supported and selected, when the admin moves participants, then group membership updates before tournament start.

AC-39: [Later Scope] Advancement rules  
Given group stage is complete, when defined advancement rules are applied, then the correct number of participants advances to the final stage.

AC-40: [Later Scope] Final stage creation  
Given qualified participants are known, when the admin starts the final stage, then the final stage bracket is generated.

### K. Communication

AC-41: [Later Scope] Announcements  
Given announcements are supported, when I am an admin and post an announcement, then it appears on the tournament page.

AC-42: [Later Scope] Participant messages  
Given messaging is supported and enabled, when admins send a tournament-related message, then selected participants receive it or can view it.

AC-43: [MVP] Public match updates  
Given an assigned participant or admin saves an active-match result or an admin corrects a completed result, when admins, participants, or spectators load or manually refresh the public tournament page, then it shows the saved match participants, completed state, and result; any resulting bracket advancement or next-match participant or pending source; and any affected standings record, match points, rank, and applicable tiebreaker values. Already-open pages are not required to update automatically; MVP public match updates are refresh-based and do not require real-time push or polling.

### L. Completion and correction

AC-44: [MVP] End tournament  
Given all required matches are complete, when the admin ends the tournament, then final results and placements are published.

AC-45: [MVP] Prevent early completion  
Given required matches are incomplete, when the admin tries to end the tournament, then the system warns the admin and requires completion before final results are published.

AC-46: [MVP] Admin correct completed match result

Given a match is completed and the tournament is not cancelled, when an admin enters a valid replacement result, then the system shows its effect on standings, final placements, and unfinished competition and requires confirmation before saving it. If the correction would change the entrant, opponent, or pairing of a completed downstream match, then the system blocks the correction and explains why. Otherwise, the saved match remains completed, affected standings and final placements recalculate, and only affected not-ready or active competition reflows. Participants cannot edit completed match results.

AC-47: [MVP] Completed tournament immutability

Given a tournament is completed, when any user attempts to change its participants, setup, seeds, matches, scores, standings, or placements, then the system blocks the change, except that an admin may edit a participant's faction or faction-specific rules text without changing competitive data, or correct a completed match result under AC-46.

AC-48: [MVP] Cancel tournament

Given a tournament is not completed or cancelled, when an admin confirms cancellation, then it enters cancelled, all tournament actions are blocked, and existing records remain read-only; a previously published tournament remains public while a cancelled draft remains private.

### M. Sharing and viewing

AC-49: [MVP] Public tournament viewing

Given a tournament is published, when a spectator opens the tournament page in registration open, registration closed, in progress, completed, or cancelled status, then they can view tournament details, participants, bracket or standings, match results, and tournament status; final results are visible when completed.

AC-50: [Later Scope] Printable bracket  
Given printable brackets are supported and a bracket exists, when the admin selects print view, then a printer-friendly version is available.

AC-51: [Later Scope] Shareable result  
Given shareable result links or images are supported and a match or tournament result exists, when an admin, participant, or spectator shares it, then the shared view reflects the current result.

# MVP Recommendation

The first release should include:

1.  Private draft creation, explicit publication, and public tournament pages.
2.  Single elimination, round robin, and Swiss.
3.  Participant joining, pre-start withdrawal, and pending placement for in-progress joins.
4.  Manual and bulk participant entry by admins, including optional faction and faction-specific rules text.
5.  Admin participant editing and removal before start, with admin faction-detail editing allowed in every non-cancelled state.
6.  Controlled late placement that preserves completed history.
7.  Manual and shuffled seeding with automatically regenerated admin-only previews.
8.  Registration closure, tournament start, and admin-started rounds.
9.  Direct score reporting by an assigned participant or admin.
10. Confirmed admin correction of completed match results that preserves completed downstream competition.
11. Atomic bracket advancement, standings, and tiebreaker updates.
12. Tournament cancellation and immutable completed final results, except for noncompetitive faction metadata and constrained completed-match corrections.
13. Spectator viewing of published public tournaments.
14. Final results publishing only after every required match is complete.

Later releases should add:

1.  Private tournaments and participant invitations.
2.  Check-in and custom registration fields.
3.  Match proof attachments, disputes, and result review.
4.  Two-stage tournaments.
5.  Substitutions, forfeits, and after-start participant changes beyond controlled late placement.
6.  Broader admin overrides for ongoing tournament issues beyond completed-match corrections.
7.  Tournament templates.
8.  Printable brackets and shareable bracket or result links/images.
9.  Army/list submission, table assignment, structured round content, round timing, and late-arrival handling.
