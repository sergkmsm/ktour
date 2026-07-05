# Tournament Management System — Product Document Pack

## 3. PRD / Feature Backlog

### Product name

Working name: **BracketFlow**

### Product summary

BracketFlow is a tournament management platform that helps admins create, run, and publish public Tabletop Wargames tournaments with participant joining, admin participant management, score reporting, standings, and final results.

### MVP goal

The MVP should support the full lifecycle of a basic tournament:

Create public tournament → configure public page → add or register participants → handle withdrawals/removals → seed participants → preview bracket → start tournament → report scores → advance matches → publish final results.

### MVP feature backlog

| Priority | Feature                     | Description                                                                                                                  |
|----------|-----------------------------|------------------------------------------------------------------------------------------------------------------------------|
| P0       | Tournament creation         | Admin can create a public tournament with name, description, game system/activity, start date, and rules summary.             |
| P0       | Tournament format selection | Admin can choose single elimination, round robin, or Swiss.                                                                  |
| P0       | Public tournament page      | System displays tournament details, participants, bracket or standings, match list, tournament status, and final results.     |
| P0       | Participant joining         | Participant can join a public tournament while joining is open.                                                              |
| P0       | Participant withdrawal      | Participant can withdraw from a public tournament before the tournament starts.                                               |
| P0       | Participant manual add      | Admin can add participants by display name.                                                                                  |
| P0       | Bulk participant add        | Admin can paste a participant list and create entries quickly.                                                               |
| P0       | Participant editing         | Admin can edit display names and participant details before tournament start.                                                |
| P0       | Participant removal         | Admin can remove a participant before start and see participant withdrawals before generating the bracket or schedule.        |
| P0       | Seeding management          | Admin can manually reorder seeds or shuffle seeds.                                                                           |
| P0       | Bracket preview             | Admin can preview the bracket or scheduled pairings before starting the tournament.                                          |
| P0       | Start tournament            | Admin can lock core setup and begin matches.                                                                                 |
| P0       | Admin score reporting       | Admin can enter match results and advance winners or update standings.                                                       |
| P0       | Standings                   | System displays wins, losses, ties, points, ranking, and relevant tiebreakers for formats that use standings.                |
| P0       | End tournament              | Admin can mark tournament as complete and publish final placements.                                                          |
| P0       | Spectator viewing           | Unregistered spectators can view public tournament pages, brackets, standings, participants, match results, and final results. |

### P1 feature backlog

| Priority | Feature                    | Description                                                                                                |
|----------|----------------------------|------------------------------------------------------------------------------------------------------------|
| P1       | Private tournament option  | Admin can restrict tournament visibility and registration after MVP public tournament flows are stable.     |
| P1       | Participant invitation     | Admin can invite participants using account identity or contact information.                               |
| P1       | Check-in                   | Admin can require participants to confirm attendance before the tournament starts.                         |
| P1       | Custom registration fields | Admin can collect required details such as gamer tag, region, waiver acknowledgment, or preferred contact. |
| P1       | Substitution               | Admin can replace a participant before or during tournament operations.                                    |
| P1       | Forfeit handling           | Admin can mark a match as forfeited and advance the correct participant.                                   |
| P1       | Match attachments          | Admin or participant can attach result proof when allowed.                                                 |
| P1       | Participant self-reporting | Admin can allow participants to submit scores.                                                             |
| P1       | Score dispute status       | Match can be flagged for review when submitted scores conflict or need confirmation.                       |
| P1       | Controlled admin overrides | Admin can correct operational issues during an ongoing tournament, such as score mistakes, match state errors, drops, or manual advancement, with confirmation and visible correction context. |
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

MVP should support the following tournament structures:

1.  **Single elimination** — one loss eliminates the participant.
2.  **Round robin** — each participant plays every other participant in the tournament.
3.  **Swiss** — participants play a set number of rounds and are paired with competitors who have similar records.

Later scope may add free-for-all, leaderboard, two-stage, and racing formats after the MVP formats are fully specified.

#### Registration rules

MVP should allow admins to choose:

- Joining open or closed.

Private registration, registration deadlines, participant limits, waitlists, custom participant fields, check-in, region restrictions, and admin approval rules are later-scope items that need separate clarification.

#### Match lifecycle

Each match should have clear states. The exact transitions, guard rules, and boundaries between similar states are unresolved and tracked in `06-open-questions-and-problems.md`.

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

#### Admin operations and overrides

BracketFlow should give admins practical control to keep a real tournament moving when the system state no longer matches what happened at the event. These controls should be powerful enough to correct common operational problems, but not so unrestricted that they silently rewrite tournament history.

Controlled admin override behavior should include:

1.  Clear confirmation before changing completed matches, bracket progression, standings, or final placements.
2.  Visible correction context for affected admins, participants, and spectators when published information changes.
3.  Guardrails for high-impact changes, such as changing format, removing large parts of bracket history, or altering completed final results.
4.  A preference for explicit admin decisions over hidden automatic recovery when a correction has downstream effects.

#### Tournament lifecycle

Each tournament should have clear states. The exact transitions, guard rules, and release-specific state set are unresolved and tracked in `06-open-questions-and-problems.md`.

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
