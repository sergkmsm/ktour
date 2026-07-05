# Tournament Management System — Product Document Pack

## 3. PRD / Feature Backlog

### Product name

Working name: **BracketFlow**

### Product summary

BracketFlow is a tournament management platform that helps admins create, run, and publish tournaments with flexible formats, registration, check-in, participant management, score reporting, and standings.

### MVP goal

The MVP should support the full lifecycle of a basic tournament:

Create tournament → add/register participants → seed participants → start bracket → report scores → advance matches → publish final results.

### MVP feature backlog

| Priority | Feature                     | Description                                                                                                     |
|----------|-----------------------------|-----------------------------------------------------------------------------------------------------------------|
| P0       | Tournament creation         | Admin can create a tournament with name, description, game/activity, start date, visibility, and rules summary. |
| P0       | Tournament format selection | Admin can choose single elimination, double elimination, round robin, or Swiss.                                 |
| P0       | Public tournament page      | System displays bracket, participants, standings, match list, announcements, and tournament status.             |
| P0       | Private tournament option   | Admin can restrict tournament visibility and registration.                                                      |
| P0       | Participant manual add      | Admin can add participants by display name.                                                                     |
| P0       | Participant invitation      | Admin can invite participants using account identity or contact information.                                    |
| P0       | Bulk participant add        | Admin can paste a participant list and create entries quickly.                                                  |
| P0       | Participant editing         | Admin can edit display names and participant details before tournament start.                                   |
| P0       | Participant removal         | Admin can remove a participant before start or mark a participant as dropped after start.                       |
| P0       | Seeding management          | Admin can manually reorder seeds or shuffle seeds.                                                              |
| P0       | Bracket preview             | Admin can preview the bracket before starting the tournament.                                                   |
| P0       | Start tournament            | Admin can lock core setup and begin matches.                                                                    |
| P0       | Score reporting             | Admin can enter match results and advance winners.                                                              |
| P0       | Standings                   | System displays wins, losses, ties, points, ranking, and relevant tiebreakers.                                  |
| P0       | End tournament              | Admin can mark tournament as complete and publish final placements.                                             |

### P1 feature backlog

| Priority | Feature                    | Description                                                                                                |
|----------|----------------------------|------------------------------------------------------------------------------------------------------------|
| P1       | Registration page          | Admin can open a sign-up page where participants register themselves.                                      |
| P1       | Check-in                   | Admin can require participants to confirm attendance before the tournament starts.                         |
| P1       | Custom registration fields | Admin can collect required details such as gamer tag, region, waiver acknowledgment, or preferred contact. |
| P1       | Substitution               | Admin can replace a participant before or during tournament operations.                                    |
| P1       | Forfeit handling           | Admin can mark a match as forfeited and advance the correct participant.                                   |
| P1       | Match attachments          | Admin or participant can attach result proof when allowed.                                                 |
| P1       | Participant self-reporting | Admin can allow participants to submit scores.                                                             |
| P1       | Score dispute status       | Match can be flagged for review when submitted scores conflict or need confirmation.                       |
| P1       | Announcements              | Admin can post tournament-wide messages.                                                                   |

### P2 feature backlog

| Priority | Feature                     | Description                                                                           |
|----------|-----------------------------|---------------------------------------------------------------------------------------|
| P2       | Two-stage tournaments       | Admin can run group stage to final stage tournaments.                                 |
| P2       | Group assignment            | Admin can assign groups automatically or manually.                                    |
| P2       | Advancement rules           | Admin can define how many participants advance from each group.                       |
| P2       | Additional formats          | Free-for-all, leaderboard, time trial, single race, and grand prix.                   |
| P2       | Multiple sets per match     | Admin can define best-of or multi-set match scoring.                                  |
| P2       | Placement matches           | Admin can create 3rd place or extended placement matches.                             |
| P2       | Tournament templates        | Admin can reuse settings from a prior tournament.                                     |
| P2       | Printable bracket           | Admin can generate a printer-friendly bracket.                                        |
| P2       | Shareable bracket/results   | Admins, participants, and spectators can share bracket or match result links/images.  |
| P2       | Reopen completed tournament | Admin can reopen a completed tournament to correct scores or rankings.                |
| P2       | Region restriction          | Admin can restrict registration to selected regions or countries.                     |
| P2       | Blocklist                   | Admin can prevent selected participants from registering.                             |
| P2       | Paid registration           | Admin can set an entry fee and track who has completed registration payment.          |
| P2       | Sponsor display             | Admin can display sponsor information on the tournament page.                         |

### Feature notes

#### Tournament formats

The system should support the following tournament structures:

1.  **Single elimination** — one loss eliminates the participant.
2.  **Double elimination** — participant is eliminated after two losses.
3.  **Round robin** — each participant plays every other participant in a group or tournament.
4.  **Swiss** — participants play a set number of rounds and are paired with competitors who have similar records.
5.  **Free-for-all** — multiple competitors compete in a match and top performers advance.
6.  **Leaderboard** — participants accumulate scores and are ranked by total performance.
7.  **Two-stage** — participants compete in groups first, then qualifying participants advance to a final stage.
8.  **Racing formats** — single race, time trial, and grand prix.

#### Registration rules

The system should allow admins to choose:

- Registration open or closed.
- Public or private registration.
- Registration deadline.
- Maximum participants.
- Waitlist behavior.
- Required participant fields.
- Check-in required or optional.
- Region restrictions if applicable.
- Whether admin approval is required.

#### Match lifecycle

Each match should have clear states:

1.  Not ready.
2.  Waiting for participants.
3.  Ready.
4.  Ready for score reporting.
5.  In progress.
6.  Awaiting score.
7.  Score submitted.
8.  Under review.
9.  Completed.
10. Forfeited.
11. Disputed.

#### Tournament lifecycle

Each tournament should have clear states:

1.  Draft.
2.  Registration open.
3.  Registration closed.
4.  Check-in open.
5.  Ready to start.
6.  In progress.
7.  Paused.
8.  Completed.
9.  Reopened.
10. Cancelled.
