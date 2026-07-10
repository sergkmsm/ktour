# Tournament Management System — Product Document Pack

## 3. PRD / Feature Backlog

### Product name

Working name: **BracketFlow**

### Product summary

BracketFlow is a tournament management platform that helps admins create, run, and publish public Tabletop Wargames tournaments with participant joining, admin participant management, score reporting, standings, and final results.

### MVP goal

The MVP should support the full lifecycle of a basic tournament:

Create draft → configure tournament → publish as registration open or closed → add or register participants → handle pre-start withdrawals/removals → seed participants → preview bracket or schedule → close registration → start tournament and round one → start later rounds → report scores → advance matches and update standings → publish final results.

### MVP feature backlog

| Priority | Feature | Description |
|----------|---------|-------------|
| P0 | Tournament creation | Admin can create a tournament with name, description, game system/activity, start date, and rules summary; it is saved as a private draft. |
| P0 | Tournament publication | Admin can publish a valid draft into registration open or registration closed; publication makes its page public. |
| P0 | Tournament format selection | Admin can choose single elimination, round robin, or Swiss. |
| P0 | Public tournament page | System displays published tournament details, participants, bracket or standings, match list, status, and final results. |
| P0 | Participant joining | Participant can join while registration is open; an in-progress join is pending admin placement. |
| P0 | Participant withdrawal | Participant can withdraw from a public tournament before the tournament starts. |
| P0 | Participant manual add | Admin can add participants by display name. |
| P0 | Bulk participant add | Admin can paste a participant list and create entries quickly. |
| P0 | Participant editing | Admin can edit display names and participant details before tournament start. |
| P0 | Participant removal | Admin can remove a participant before start and see participant withdrawals before generating the bracket or schedule. |
| P0 | Controlled late placement | Admin can place an after-start entrant after reviewing and confirming changes to unfinished pairings and standings. |
| P0 | Seeding management | Admin can manually reorder seeds or shuffle seeds. |
| P0 | Bracket preview | Admin can preview the bracket or scheduled pairings before starting; affected setup changes regenerate the current preview. |
| P0 | Start tournament and rounds | Admin can close registration, lock competitive setup, start the tournament with round one, and start each later round. |
| P0 | Direct score reporting | An assigned participant or admin can enter an active-match result that completes the match and advances results. |
| P0 | Standings | System displays wins, losses, ties, points, ranking, and relevant tiebreakers for formats that use standings. |
| P0 | Tournament cancellation | Admin can cancel a nonterminal tournament after confirmation; it becomes read-only. |
| P0 | End tournament | Admin can mark tournament as complete and publish final placements. |
| P0 | Spectator viewing | Unregistered spectators can view published tournament pages, brackets, standings, participants, match results, and final results. |

### P1 feature backlog

| Priority | Feature | Description |
|----------|---------|-------------|
| P1 | Private tournament option | Admin can restrict tournament visibility and registration after MVP public tournament flows are stable. |
| P1 | Participant invitation | Admin can invite participants using account identity or contact information. |
| P1 | Check-in | Admin can require participants to confirm attendance before the tournament starts. |
| P1 | Custom registration fields | Admin can collect required details such as gamer tag, region, waiver acknowledgment, or preferred contact. |
| P1 | Substitution | Admin can replace a participant during tournament operations. |
| P1 | Forfeit handling | Admin can mark a match as forfeited and advance the correct participant. |
| P1 | Match attachments | Admin or participant can attach result proof when allowed. |
| P1 | Score dispute status | Match can be flagged for review when submitted scores conflict or need confirmation. |
| P1 | Broader admin overrides | Admin can correct score mistakes, match-state errors, drops, or manual advancement beyond the controlled late-placement flow. |
| P1 | Announcements | Admin can post tournament-wide messages. |

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

An admin publishes a draft into registration open or registration closed. Registration must be closed to start the tournament. Once in progress, joining is open for pending-placement requests only; an admin must confirm controlled reflow before an entrant is active. Private registration, registration deadlines, participant limits, waitlists, custom participant fields, check-in, region restrictions, and admin approval rules are later-scope items that need separate clarification.

#### Match lifecycle

MVP matches use only the following states:

1.  **Not ready** — the match belongs to a round that the admin has not started.
2.  **Active** — the admin has started the match's round; an assigned participant or admin may report a valid result.
3.  **Completed** — a valid result has been saved. The result, match, and its completed history cannot be edited in MVP.

Tournament start creates the final bracket or schedule and starts round one. The admin starts every subsequent round after its prerequisites are complete. Starting a round changes its matches from not ready to active. Saving a valid result changes an active match to completed, advances bracket entrants when applicable, and immediately updates standings. Ready, ready for score reporting, in progress, awaiting score, score submitted, under review, forfeited, and disputed are not MVP match states.

#### Admin operations and overrides

During an in-progress tournament, the only MVP change to competitive participants is controlled late placement. The admin chooses the entrant's placement and confirms a preview of changes to unfinished pairings and standings. Completed match history is preserved. Format, format structure, scoring model, standings points, tiebreaker order, seed order, and bracket or schedule rules lock at start. Description, rules summary, and scheduled date/time remain editable while in progress. Completed and cancelled tournaments are fully immutable.

#### Tournament lifecycle

MVP tournament states and transitions are:

1.  **Draft** — private to its admin. A draft may be published as registration open or registration closed, or cancelled.
2.  **Registration open** — public and joinable. The admin may close or reopen registration, or cancel the tournament.
3.  **Registration closed** — public but not joinable. The admin may reopen registration, start a valid tournament, or cancel it.
4.  **In progress** — public. Starting it starts round one. Public joins become pending placement; only confirmed controlled reflow makes them active entrants. The admin may start later rounds, complete the tournament when every required match is complete, or cancel it.
5.  **Completed** — public, final, and immutable. It has no outgoing transitions.
6.  **Cancelled** — terminal and read-only. A cancelled draft remains private; a previously published tournament remains publicly viewable.

`Paused` and `Reopened` are not tournament states. `Cancelled` is the only additional MVP terminal state.
