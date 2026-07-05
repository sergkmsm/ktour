# Tournament Management System — Product Document Pack

## 4. User Stories / Use Cases

### MVP user stories

#### Epic 1: Public tournament creation

User story 1.1  
As an admin, I want to create a public tournament so that I can host a competition.

User story 1.2  
As an admin, I want to choose the tournament format so that the competition structure matches my event.

User story 1.3  
As an admin, I want to configure the public tournament page so that participants and spectators understand the event.

User story 1.4  
As an admin, I want to add tournament rules and descriptions so that participants understand how the competition works.

#### Epic 2: Participant joining and management

User story 2.1  
As an admin, I want to open or close joining so that I can control when participants can join the public tournament.

User story 2.2  
As a participant, I want to join a public tournament so that I can compete.

User story 2.3  
As a participant, I want to withdraw from a public tournament before it starts so that the admin knows I am no longer competing.

User story 2.4  
As an admin, I want to manually add participants so that I can support offline signups.

User story 2.5  
As an admin, I want to bulk-add participants so that I can quickly create a bracket from an existing list.

User story 2.6  
As an admin, I want to edit or remove participants before the tournament starts so that the tournament remains accurate.

User story 2.7  
As an admin, I want to see withdrawn participants before start so that I can make final bracket decisions.

#### Epic 3: Seeding and bracket setup

User story 3.1  
As an admin, I want to seed participants manually so that I can control bracket fairness.

User story 3.2  
As an admin, I want to shuffle seeds so that I can randomize pairings.

User story 3.3  
As an admin, I want to preview the bracket before starting so that I can review pairings.

User story 3.4  
As a participant, I want to know when the bracket is final so that I do not rely on an unfinished preview.

#### Epic 4: Match operations

User story 4.1  
As an admin, I want to see each match state so that I know what needs a result or advancement.

User story 4.2  
As an admin, I want to view match participants and bracket position so that I can manage progression accurately.

User story 4.3  
As a participant, I want to see my match opponent and status so that I understand what action is needed.

User story 4.4  
As a spectator, I want to see match participants, scores, and state so that I can follow tournament progress.

#### Epic 5: Admin score reporting and results

User story 5.1  
As an admin, I want to report scores so that the bracket advances.

User story 5.2  
As a participant, I want to see standings so that I understand my rank.

User story 5.3  
As an admin, I want tiebreakers so that tied participants can be ranked fairly.

User story 5.4  
As a spectator, I want to view the bracket and standings so that I can follow the tournament.

User story 5.5  
As an admin, I want to publish final placements so that results are official.

#### Epic 6: Spectator viewing

User story 6.1  
As a spectator, I want to open a public tournament page without registering so that I can follow the event.

User story 6.2  
As a spectator, I want to see participants, brackets, standings, match results, and final results so that I can understand the tournament outcome.

### Later-scope user stories

#### Epic 7: Private tournaments and invitations

User story 7.1  
As an admin, I want to make the tournament private so that I can control visibility and access.

User story 7.2  
As an admin, I want to invite participants so that I can run invite-only tournaments.

#### Epic 8: Check-in and richer registration

User story 8.1  
As an admin, I want to require check-in so that only confirmed participants are included.

User story 8.2  
As a participant, I want to check in before the tournament so that the admin knows I am present.

User story 8.3  
As an admin, I want to view checked-in and missing participants so that I can make final bracket decisions.

User story 8.4  
As an admin, I want to collect custom registration fields so that I have event-specific participant information.

#### Epic 9: Later match operations

User story 9.1  
As a participant, I want to submit scores when allowed so that match results can be recorded quickly.

User story 9.2  
As an admin, I want to require match proof so that disputed results can be reviewed.

User story 9.3  
As an admin, I want to review disputed scores so that the correct winner advances.

User story 9.4  
As an admin, I want to mark forfeits so that no-shows do not block the tournament.

User story 9.5  
As an admin, I want to substitute participants so that unexpected attendance changes can be handled.

#### Epic 10: Two-stage tournaments

User story 10.1  
As an admin, I want to create a group stage followed by finals so that I can run a structured tournament.

User story 10.2  
As an admin, I want to assign participants to groups automatically or manually so that groups are fair and correct.

User story 10.3  
As an admin, I want to define how many participants advance from each group so that the final stage is clear.

User story 10.4  
As a participant, I want to see my group standings and advancement status so that I know what I need to do.

#### Epic 11: Communication and correction

User story 11.1  
As an admin, I want to post announcements so that participants receive important updates.

User story 11.2  
As an admin, I want to message participants so that I can communicate tournament updates or issues.

User story 11.3  
As a participant, I want tournament updates in one place so that I do not miss bracket, result, or rule changes.

User story 11.4  
As an admin, I want to edit incorrect match results so that mistakes can be fixed.

User story 11.5  
As an admin, I want to reopen a completed tournament so that final results can be corrected.

User story 11.6  
As a participant, I want corrections to be visible so that I can trust the final standings.

User story 11.7  
As an admin, I want controlled override tools for drops, match state mistakes, and manual advancement so that real-world tournament problems can be fixed without unrestricted editing.

User story 11.8  
As a spectator, I want corrected public information to show that an update happened so that tournament progress remains trustworthy.

User story 11.9  
As an admin, I want important corrections to require confirmation so that I do not accidentally change brackets, standings, or final placements.

### Key use cases

#### Use case A: Create a public MVP tournament

Actor: Admin  
Goal: Create and publish a public tournament.

Main flow:

1.  Admin creates a tournament.
2.  Admin enters tournament name, description, game/activity, date, and rules.
3.  Admin selects single elimination, round robin, or Swiss.
4.  Admin configures the public tournament page.
5.  Admin opens joining or adds participants manually or in bulk.
6.  Admin reviews joined, withdrawn, and admin-added participants.
7.  Admin sets or shuffles seeds.
8.  Admin previews the bracket or scheduled pairings.
9.  Admin starts the tournament.

Successful outcome: Tournament is started and ready for match results.

#### Use case B: Join or withdraw from a tournament

**Actor:** Participant  
**Goal:** Join or leave a public tournament before it starts.

Main flow:

1.  Participant opens tournament page.
2.  Participant selects join while joining is open.
3.  System records the participant as joined.
4.  Participant sees joined status.
5.  If the participant can no longer compete before start, participant selects withdraw.
6.  System records the participant as withdrawn.

Successful outcome: Participant and admin can see whether the participant is joined or withdrawn.

#### Use case C: Report match score

Actor: Admin  
Goal: Record match result.

Main flow:

1.  Admin opens an active match.
2.  Admin enters score.
3.  Admin selects winner if required by the format.
4.  System records the result.
5.  Bracket or standings update.

Successful outcome: Match is completed and the next match or ranking is updated.

#### Later-scope use case C2: Correct an ongoing tournament issue

Actor: Admin  
Goal: Fix a tournament state problem without restarting the event.

Main flow:

1.  Admin identifies a score, match state, participant status, or advancement problem.
2.  Admin opens the affected match or tournament control area.
3.  System explains the downstream effect on bracket progression, standings, or final placements.
4.  Admin confirms the correction.
5.  System applies the correction and updates affected public tournament information.
6.  System shows correction context where needed so affected viewers can understand that information changed.

Successful outcome: The tournament reflects the real-world event state and can continue without hidden or uncontrolled changes.

#### Use case D: View a public tournament as a spectator

Actor: Spectator  
Goal: Follow a tournament without registering.

Main flow:

1.  Spectator opens a public tournament page.
2.  Spectator views tournament details and participant list.
3.  Spectator views bracket or standings.
4.  Spectator views match results and current tournament status.
5.  Spectator views final results after completion.

Successful outcome: Spectator can understand tournament progress and final outcome without taking tournament actions.

#### Later-scope use case E: Run a two-stage tournament

Actor: Admin  
Goal: Run group stage followed by final stage.

Main flow:

1.  Admin selects two-stage format.
2.  Admin selects group stage format.
3.  Admin selects final stage format.
4.  Admin assigns participants to groups.
5.  Admin defines advancement count per group.
6.  Admin starts group stage.
7.  Scores are reported.
8.  Group standings are finalized.
9.  Qualified participants advance to final stage.
10. Final stage is completed.

Successful outcome: Tournament produces final placements after both stages.
