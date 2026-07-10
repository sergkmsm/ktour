# Tournament Management System — Product Document Pack

## 5. Acceptance Criteria

### A. Tournament creation

AC-1: [MVP] Create tournament draft

Given I am an admin, when I create a tournament with required basic information, then the tournament is saved as a draft.

AC-2: [MVP] Required fields  
Given I am creating a tournament, when required fields are missing, then I cannot publish or start the tournament until those fields are completed.

AC-3: [MVP] Format selection  
Given I am creating a tournament, when I select single elimination, round robin, or Swiss, then the system shows the setup options required for that format before start.

AC-4: [MVP] Publish public tournament

Given a valid draft, when the admin publishes it as registration open or registration closed, then its public page becomes visible; the draft is visible only to its admin before publication.

### B. Joining

AC-5: [MVP] Open joining  
Given joining is open for a public tournament, when a participant submits the required MVP join information, then they are added with joined status during registration open or pending-placement status during in-progress play.

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

AC-11: [MVP] Edit participant before start  
Given the tournament has not started, when the admin edits a participant display name, then the updated name appears in the bracket preview and participant list.

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
Given participants exist before start, when the admin changes seed order, then the admin-only bracket preview or scheduled pairings regenerate automatically.

AC-19: [MVP] Shuffle seeding  
Given participants exist before start, when the admin shuffles seeds, then participant order changes and the system automatically regenerates the admin-only preview before starting.

AC-20: [MVP] Final bracket lock  
Given the tournament starts, when the final bracket or scheduled pairings are generated, then viewers can distinguish them from earlier previews; format, structure, scoring, standings, tiebreakers, seeds, and bracket or schedule rules are locked.

### F. Tournament start

AC-21: [MVP] Start tournament  
Given registration is closed and required setup is complete, when the admin starts the tournament, then the final bracket or schedule is created, the tournament enters in progress, and first-round matches become active.

AC-22: [MVP] Prevent invalid start  
Given registration is open, required setup is incomplete, seeding is invalid, or the selected format lacks enough active participants, when the admin attempts to start the tournament, then the system prevents the start and explains what must be fixed.

### G. Match operations

AC-23: [MVP] Match page  
Given a match exists, when an admin, participant, or spectator views it, then they can see participants, score status, bracket or standings context, and its not-ready, active, or completed state.

AC-24: [MVP] Match state visibility  
Given match states change during the MVP flow, when admins, participants, or spectators view the tournament, then they can see whether each match is not ready, active, or completed.

AC-25: [MVP] Round activation

Given a future round's prerequisites are complete, when an admin starts that round, then its not-ready matches become active and only assigned participants or admins can report their results.

AC-26: [MVP] Match context and upcoming visibility

Given a match exists or a participant has a future match generated by the bracket or schedule, when they view the tournament, then they can understand its progression position and see its opponent or pending source.

### H. Score reporting

AC-27: [MVP] Direct score reporting

Given a match is active, when an assigned participant or admin enters a result that fits the selected format's scoring fields, then the system saves it, completes the match, advances the winner when applicable, and updates standings.

AC-28: [MVP] Invalid score  
Given a score does not fit the selected format's scoring fields, when an assigned participant or admin submits it, then the score is rejected with a clear explanation and the match remains active.

AC-29: [MVP] Participant self-reporting

Given an assigned participant submits a valid result for an active match, when it is saved, then it is final immediately without a confirmation or review state.

AC-30: [Later Scope] Match proof  
Given proof is supported and required, when a score is submitted without proof, then the score cannot be finalized.

AC-31: [Later Scope] Disputed score  
Given disputes are supported and submitted scores conflict or are challenged, when a dispute is opened, then the match enters review status and does not advance until an admin resolves it.

AC-32: [Later Scope] Forfeit  
Given forfeits are supported, when the admin marks a forfeit, then the opponent advances or receives the defined result.

### I. Standings and tiebreakers

AC-33: [MVP] Standings update  
Given a valid match result is saved, when standings are displayed, then wins, losses, ties, points, and rank reflect that result in the same completed-match operation.

AC-34: [MVP] Tiebreakers  
Given participants are tied and the admin has selected an ordered tiebreaker list before start, when standings are calculated, then those tiebreakers are applied in order.

AC-35: [MVP] Tiebreaker visibility  
Given tiebreakers affect ranking, when admins, participants, or spectators view standings, then the applied tiebreaker values or explanation are visible.

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
Given an assigned participant or admin saves a result for an active match, when admins, participants, or spectators view the public tournament page, then the current saved match information is shown.

### L. Completion and correction

AC-44: [MVP] End tournament  
Given all required matches are complete, when the admin ends the tournament, then final results and placements are published.

AC-45: [MVP] Prevent early completion  
Given required matches are incomplete, when the admin tries to end the tournament, then the system warns the admin and requires completion before final results are published.

AC-46: [MVP] Prevent completed match edits

Given a match is completed, when an admin or participant attempts to change its result or state, then the system blocks the change.

AC-47: [MVP] Completed tournament immutability

Given a tournament is completed, when any user attempts to change its participants, setup, seeds, matches, scores, standings, or placements, then the system blocks the change.

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
4.  Manual and bulk participant entry by admins, including controlled late placement that preserves completed history.
5.  Admin participant editing and removal before start.
6.  Manual and shuffled seeding with automatically regenerated admin-only previews.
7.  Registration closure, tournament start, and admin-started rounds.
8.  Direct score reporting by an assigned participant or admin.
9.  Atomic bracket advancement, standings, and tiebreaker updates.
10. Tournament cancellation and immutable completed final results.
11. Spectator viewing of published public tournaments.
12. Final results publishing only after every required match is complete.

Later releases should add:

1.  Private tournaments and participant invitations.
2.  Check-in and custom registration fields.
3.  Match proof attachments, disputes, and result review.
4.  Two-stage tournaments.
5.  Substitutions, forfeits, and after-start participant changes beyond controlled late placement.
6.  Broader admin overrides for ongoing tournament issues.
7.  Tournament templates.
8.  Printable brackets and shareable bracket or result links/images.
