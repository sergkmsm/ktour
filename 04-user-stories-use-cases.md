# Tournament Management System — Product Document Pack

## 4. User Stories / Use Cases

### MVP user stories

#### Epic 1: Public tournament creation

User story 1.1  
As an admin, I want to create a tournament as a private draft so that I can configure it before it is public.

User story 1.2  
As an admin, I want to choose the tournament format so that the competition structure matches my event.

User story 1.3  
As an admin, I want to configure the public tournament page so that participants and spectators understand the event.

User story 1.4  
As an admin, I want to add tournament rules and descriptions so that participants understand how the competition works.

User story 1.5

As an admin, I want to publish a valid draft into registration open or registration closed so that participants and spectators can access the tournament page.

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

User story 2.8

As an admin, I want to place an entrant who joined after start only after I review its effect on unfinished pairings and standings.

User story 2.9

As a participant, I want to see when my after-start join is pending admin placement so that I know I am not yet active in the tournament.

User story 2.10

As an admin, I want to record and correct a participant's optional faction and faction-specific rules text in every non-cancelled tournament state so that tournament information remains accurate without changing competition results.

#### Epic 3: Seeding and bracket setup

User story 3.1  
As an admin, I want to seed participants manually so that I can control bracket fairness.

User story 3.2  
As an admin, I want to shuffle seeds so that I can randomize pairings.

User story 3.3  
As an admin, I want an automatically updated private preview before starting so that I can review current pairings.

User story 3.4  
As a participant, I want to know when the final bracket or schedule has started so that I do not rely on an unfinished preview.

#### Epic 4: Match operations

User story 4.1  
As an admin, I want to start each round so that only its matches become active.

User story 4.2  
As an admin, I want to view match participants and bracket position so that I can manage progression accurately.

User story 4.3  
As a participant, I want to see my match opponent and status so that I understand what action is needed.

User story 4.4  
As a spectator, I want to see match participants, scores, and state so that I can follow tournament progress.

#### Epic 5: Score reporting and results

User story 5.1  
As an admin or assigned participant, I want to report a valid score for an active match so that the bracket advances or standings update.

User story 5.2  
As a participant, I want to see standings so that I understand my rank.

User story 5.3  
As an admin, I want tiebreakers so that tied participants can be ranked fairly.

User story 5.4  
As a spectator, I want to view the bracket and standings so that I can follow the tournament.

User story 5.5  
As an admin, I want to publish final placements so that results are official.

User story 5.6

As an admin, I want to cancel a nonterminal tournament so that no further tournament actions can occur when the event cannot continue.

User story 5.7

As an admin, I want to correct a completed match result after reviewing its impact so that I can fix mistakes without changing completed downstream matches.

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
As an admin, I want to require match proof so that disputed results can be reviewed.

User story 9.2

As an admin, I want to review disputed scores so that the correct winner advances.

User story 9.3

As an admin, I want to mark forfeits so that no-shows do not block the tournament.

User story 9.4

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

#### Epic 11: Communication and broader operations

User story 11.1  
As an admin, I want to post announcements so that participants receive important updates.

User story 11.2  
As an admin, I want to message participants so that I can communicate tournament updates or issues.

User story 11.3  
As a participant, I want tournament updates in one place so that I do not miss bracket, result, or rule changes.

User story 11.4  
As an admin, I want operational correction tools beyond controlled late placement and completed-match corrections so that future releases can handle real-world problems.

User story 11.5  
As a participant, I want any future operational correction to be visible so that I can trust published tournament information.

### Key use cases

#### Use case A: Create a public MVP tournament

Actor: Admin
Goal: Create and publish a public tournament.

Main flow:

1.  Admin creates a private draft.
2.  Admin enters tournament name, description, game/activity, date, and rules.
3.  Admin selects single elimination, round robin, or Swiss.
4.  Admin configures the public tournament page.
5.  Admin publishes the draft as registration open or registration closed.
6.  Admin opens joining if needed, or adds participants manually or in bulk; the admin may add optional faction and faction-specific rules text for a participant.
7.  Admin reviews joined, withdrawn, and admin-added participants.
8.  Admin sets or shuffles seeds.
9.  System automatically regenerates the admin-only bracket or schedule preview after affected changes.
10. Admin closes registration.
11. Admin starts the tournament, which finalizes the bracket or schedule and starts round one.

Successful outcome: Tournament is in progress with round one active and ready for match results.

#### Use case B: Join or withdraw from a tournament

**Actor:** Participant  
**Goal:** Join a public tournament, or leave before it starts.

Main flow:

1.  Participant opens tournament page.
2.  Participant selects join while joining is open.
3.  If registration is open, the system records the participant as joined.
4.  If the tournament is in progress, the system records the participant as pending placement until an admin confirms controlled reflow.
5.  Participant sees joined or pending-placement status.
6.  If the participant can no longer compete before start, participant selects withdraw.
7.  System records the participant as withdrawn.

Successful outcome: Participant and admin can see whether the participant is joined, pending placement, or withdrawn.

#### Use case C: Report match score

Actor: Admin or assigned participant

Goal: Record match result.

Main flow:

1.  Reporter opens an active match.
2.  Reporter enters score.
3.  Reporter selects winner if required by the format.
4.  System validates and records the result, then completes the match.
5.  Bracket advancement and standings update atomically.

Successful outcome: Match is completed and the next match or ranking is updated.

#### Use case C1: Correct a completed match result

Actor: Admin
Goal: Correct a completed result without rewriting completed downstream competition.

Main flow:

1.  Admin opens a completed match in a non-cancelled tournament.
2.  Admin enters a valid replacement result.
3.  System shows the effect on standings, final placements, and unfinished competition.
4.  If the correction would change a completed downstream match or pairing, the system blocks it and explains why.
5.  Otherwise, the admin confirms the correction.
6.  System saves the result, recalculates standings and final placements, and reflows only affected not-ready or active competition.

Successful outcome: The completed result is corrected without changing any completed downstream match or pairing.

#### Use case C2: Place an after-start entrant

Actor: Admin  
Goal: Add an entrant to unfinished competition without changing completed history.

Main flow:

1.  A participant joins while the tournament is in progress, or the admin adds an entrant.
2.  System shows the entrant as pending placement.
3.  Admin selects a placement in the unfinished competition.
4.  System shows the effect on unfinished pairings and standings.
5.  Admin confirms the placement.
6.  System regenerates only affected unfinished competition and marks the entrant active.

Successful outcome: The tournament includes the entrant without changing completed matches or results.

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
