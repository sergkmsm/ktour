# Tournament Management System — Product Document Pack

## 5. Acceptance Criteria

### A. Tournament creation

AC-1: [MVP] Create public tournament  
Given I am an admin, when I create a public tournament with required basic information, then the tournament is saved as a draft.

AC-2: [MVP] Required fields  
Given I am creating a tournament, when required fields are missing, then I cannot publish or start the tournament until those fields are completed.

AC-3: [MVP] Format selection  
Given I am creating a tournament, when I select single elimination, round robin, or Swiss, then the system shows the setup options required for that format before start.

AC-4: [Later Scope] Private visibility  
Given private tournaments are supported, when I choose private visibility, then the tournament is not publicly discoverable and access is controlled by later-scope private tournament rules.

### B. Joining

AC-5: [MVP] Open joining  
Given joining is open for a public tournament, when a participant submits the required MVP join information, then they are added to the participant list with joined status.

AC-6: [MVP] Joining closed  
Given joining is closed, when a participant visits the tournament page, then they cannot join and must see the joining status.

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

AC-12: [Later Scope] Substitute participant  
Given substitution is supported, when the admin replaces a participant, then the new participant takes the correct bracket or group position according to defined substitution rules.

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
Given participants exist, when the admin changes seed order, then the bracket preview or scheduled pairings update.

AC-19: [MVP] Shuffle seeding  
Given participants exist, when the admin shuffles seeds, then participant order changes and the admin can review the updated bracket preview or scheduled pairings before starting.

AC-20: [MVP] Final bracket lock  
Given the tournament has started, when the bracket or scheduled pairings are generated, then participants can distinguish final matches from earlier previews.

### F. Tournament start

AC-21: [MVP] Start tournament  
Given required setup is complete, when the admin starts the tournament, then active first-round matches or first-round pairings are created.

AC-22: [MVP] Prevent invalid start  
Given required setup is incomplete, when the admin attempts to start the tournament, then the system explains what must be fixed.

### G. Match operations

AC-23: [MVP] Match page  
Given a match exists, when an admin, participant, or spectator views it, then they can see participants, score status, bracket or standings context, and current state.

AC-24: [MVP] Match state visibility  
Given match states change during the MVP flow, when admins, participants, or spectators view the tournament, then they can see whether each match is pending, active, or completed.

AC-25: [MVP] Match bracket position  
Given a match exists, when admins, participants, or spectators view the bracket or match page, then they can understand where the match sits in tournament progression.

AC-26: [MVP] Upcoming match visibility  
Given a participant has a future match generated by the bracket or schedule, when they view the tournament, then they can see the opponent or pending source of that match.

### H. Score reporting

AC-27: [MVP] Admin score reporting  
Given a match is ready for score reporting, when an admin enters a result that fits the selected format's scoring fields, then the match is completed and the winner advances or standings update.

AC-28: [MVP] Invalid score  
Given a score does not fit the selected format's scoring fields, when an admin submits it, then the score is rejected with a clear explanation.

AC-29: [Later Scope] Participant self-reporting  
Given self-reporting is supported and enabled, when a participant submits a score, then the match is updated according to defined confirmation or review rules.

AC-30: [Later Scope] Match proof  
Given proof is supported and required, when a score is submitted without proof, then the score cannot be finalized.

AC-31: [Later Scope] Disputed score  
Given disputes are supported and submitted scores conflict or are challenged, when a dispute is opened, then the match enters review status and does not advance until an admin resolves it.

AC-32: [Later Scope] Forfeit  
Given forfeits are supported, when the admin marks a forfeit, then the opponent advances or receives the defined result.

### I. Standings and tiebreakers

AC-33: [MVP] Standings update  
Given a match result is submitted, when standings are displayed, then wins, losses, ties, points, and rank reflect the latest saved result.

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
Given an admin changes a match score or match state, when admins, participants, or spectators view the public tournament page, then the current saved match information is shown.

### L. Completion and correction

AC-44: [MVP] End tournament  
Given all required matches are complete, when the admin ends the tournament, then final results and placements are published.

AC-45: [MVP] Prevent early completion  
Given required matches are incomplete, when the admin tries to end the tournament, then the system warns the admin and requires completion before final results are published.

AC-46: [Later Scope] Edit result  
Given result correction is supported and a score was entered incorrectly, when the admin edits the result, then bracket progression or standings update according to defined correction rules.

AC-47: [Later Scope] Reopen tournament  
Given tournament reopening is supported and a tournament is completed, when the admin reopens it, then results can be corrected and republished.

AC-48: [Later Scope] Correction visibility  
Given completed result correction is supported and a completed result is changed, when admins, participants, or spectators view the tournament, then the updated result and correction status are visible.

### M. Sharing and viewing

AC-49: [MVP] Public bracket viewing  
Given a tournament is public, when a spectator opens the tournament page, then they can view tournament details, participants, bracket or standings, match results, tournament status, and final results.

AC-50: [Later Scope] Printable bracket  
Given printable brackets are supported and a bracket exists, when the admin selects print view, then a printer-friendly version is available.

AC-51: [Later Scope] Shareable result  
Given shareable result links or images are supported and a match or tournament result exists, when an admin, participant, or spectator shares it, then the shared view reflects the current result.

# MVP Recommendation

The first release should include:

1.  Public tournament creation and public tournament pages.
2.  Single elimination, round robin, and Swiss.
3.  Participant joining and withdrawal before start.
4.  Manual and bulk participant entry by admins.
5.  Admin participant editing and removal before start.
6.  Manual and shuffled seeding.
7.  Bracket or schedule preview and start tournament.
8.  Admin score reporting.
9.  Standings and tiebreakers.
10. Spectator viewing of public tournaments.
11. Final results publishing.

Later releases should add:

1.  Private tournaments and participant invitations.
2.  Check-in and custom registration fields.
3.  Participant self-reporting.
4.  Match proof attachments, disputes, and result review.
5.  Two-stage tournaments.
6.  Substitutions, forfeits, and after-start participant changes.
7.  Tournament templates and correction/reopen workflows.
8.  Printable brackets and shareable bracket or result links/images.
