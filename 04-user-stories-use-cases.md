# Tournament Management System — Product Document Pack

## 4. User Stories / Use Cases

### Epic 1: Tournament creation

User story 1.1  
As an admin, I want to create a tournament so that I can host a competition.

User story 1.2  
As an admin, I want to choose the tournament format so that the competition structure matches my event.

User story 1.3  
As an admin, I want to make the tournament public or private so that I can control visibility.

User story 1.4  
As an admin, I want to add tournament rules and descriptions so that participants understand how the competition works.

### Epic 2: Registration and participants

User story 2.1  
As an admin, I want to open a registration page so that participants can register themselves.

User story 2.2  
As a participant, I want to register for a tournament so that I can compete.

User story 2.3  
As an admin, I want to manually add participants so that I can support offline or invite-only tournaments.

User story 2.4  
As an admin, I want to bulk-add participants so that I can quickly create a bracket from an existing list.

User story 2.5  
As an admin, I want to edit, remove, or substitute participants so that the tournament remains accurate.

### Epic 3: Check-in

User story 3.1  
As an admin, I want to require check-in so that only confirmed participants are included.

User story 3.2  
As a participant, I want to check in before the tournament so that the admin knows I am present.

User story 3.3  
As an admin, I want to view checked-in and missing participants so that I can make final bracket decisions.

### Epic 4: Seeding and bracket setup

User story 4.1  
As an admin, I want to seed participants manually so that I can control bracket fairness.

User story 4.2  
As an admin, I want to shuffle seeds so that I can randomize pairings.

User story 4.3  
As an admin, I want to preview the bracket before starting so that I can review pairings.

User story 4.4  
As a participant, I want to know when the bracket is final so that I do not rely on an unfinished preview.

### Epic 5: Two-stage tournaments

User story 5.1  
As an admin, I want to create a group stage followed by finals so that I can run a structured tournament.

User story 5.2  
As an admin, I want to assign participants to groups automatically or manually so that groups are fair and correct.

User story 5.3  
As an admin, I want to define how many participants advance from each group so that the final stage is clear.

User story 5.4  
As a participant, I want to see my group standings and advancement status so that I know what I need to do.

### Epic 6: Match operations

User story 6.1  
As an admin, I want to see each match state so that I know what needs a result, review, or advancement.

User story 6.2  
As an admin, I want to view match participants and bracket position so that I can manage progression accurately.

User story 6.3  
As a participant, I want to see my match opponent and status so that I understand what action is needed.

User story 6.4  
As a participant, I want to see when my match result is pending, submitted, reviewed, or completed.

### Epic 7: Score reporting and results

User story 7.1  
As an admin, I want to report scores so that the bracket advances.

User story 7.2  
As a participant, I want to submit scores when allowed so that match results can be recorded quickly.

User story 7.3  
As an admin, I want to require match proof so that disputed results can be reviewed.

User story 7.4  
As an admin, I want to review disputed scores so that the correct winner advances.

User story 7.5  
As an admin, I want to mark forfeits so that no-shows do not block the tournament.

### Epic 8: Standings and final results

User story 8.1  
As a participant, I want to see standings so that I understand my rank.

User story 8.2  
As an admin, I want tiebreakers so that tied participants can be ranked fairly.

User story 8.3  
As a spectator, I want to view the bracket and standings so that I can follow the tournament.

User story 8.4  
As an admin, I want to publish final placements so that results are official.

### Epic 9: Communication

User story 9.1  
As an admin, I want to post announcements so that participants receive important updates.

User story 9.2  
As an admin, I want to message participants so that I can communicate tournament updates or issues.

User story 9.3  
As a participant, I want tournament updates in one place so that I do not miss bracket, result, or rule changes.

### Epic 10: Correction and recovery

User story 10.1  
As an admin, I want to edit incorrect match results so that mistakes can be fixed.

User story 10.2  
As an admin, I want to reopen a completed tournament so that final results can be corrected.

User story 10.3  
As a participant, I want corrections to be visible so that I can trust the final standings.

### Key use cases

#### Use case A: Create a basic tournament

Actor: Admin  
Goal: Create and publish a tournament.

Main flow:

1.  Admin creates a tournament.
2.  Admin enters tournament name, description, game/activity, date, and rules.
3.  Admin selects format.
4.  Admin chooses public or private visibility.
5.  Admin adds participants or opens registration.
6.  Admin reviews participants.
7.  Admin sets seeds.
8.  Admin previews bracket.
9.  Admin starts tournament.

Successful outcome: Tournament is started and ready for match results.

#### Use case B: Register and check in

**Actor:** Participant  
**Goal:** Join and confirm attendance.

Main flow:

1.  Participant opens tournament page.
2.  Participant selects registration.
3.  Participant enters required registration information.
4.  Participant receives registered status.
5.  When check-in opens, participant checks in.
6.  Participant receives checked-in status.

Successful outcome: Participant is confirmed for the tournament.

#### Use case C: Report match score

Actor: Admin or participant  
Goal: Record match result.

Main flow:

1.  Admin opens an active match, or a participant opens their own active match when self-reporting is allowed.
2.  Admin or participant enters score.
3.  Admin or participant selects winner if required.
4.  Admin or participant attaches proof if required.
5.  System records the result.
6.  Bracket or standings update.

Successful outcome: Match is completed and the next match or ranking is updated.

#### Use case D: Run a two-stage tournament

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
