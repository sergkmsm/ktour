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
| P0 | Participant editing | Admin can edit display names and participant details before tournament start; faction and faction-specific rules text remain editable in every non-cancelled tournament state. |
| P0 | Participant removal | Admin can remove a participant before start and see participant withdrawals before generating the bracket or schedule. |
| P0 | Controlled late placement | Admin can place an after-start entrant after reviewing and confirming changes to unfinished pairings and standings. |
| P0 | Seeding management | Admin can manually reorder seeds or shuffle seeds. |
| P0 | Bracket preview | Admin can preview the bracket or scheduled pairings before starting; affected setup changes regenerate the current preview. |
| P0 | Start tournament and rounds | Admin can close registration, lock competitive setup, start the tournament with round one, and start each later round. |
| P0 | Direct score reporting | An assigned participant or admin can enter an active-match result that completes the match and advances results. |
| P0 | Completed match correction | Admin can correct a completed match result after reviewing and confirming the effect on standings and unfinished competition; a correction cannot alter a completed downstream match or pairing. |
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
| P1 | Broader admin overrides | Admin can correct match-state errors, drops, or manual advancement beyond the MVP completed-match correction and controlled late-placement flows. |
| P1 | Announcements | Admin can post tournament-wide messages. |
| P1 | Army/list submission | Participant army or list submission, review, and visibility can be supported after MVP. |
| P1 | Table assignment | Admin can assign tables or locations to matches, with any needed table-management controls. |
| P1 | Structured round content | Admin can define missions, scenarios, deployment maps, or round packets. |
| P1 | Round timing and late arrivals | Admin can schedule or time rounds and handle late arrivals. |

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

#### MVP format mechanics

MVP captures only a match outcome: win, loss, or, for round robin and Swiss, draw. It does not capture battle points, victory points, margin of victory, sportsmanship, painting, composition, or other game-specific scoring metrics. A win earns 3 match points, a draw earns 1 match point, and a loss earns 0 match points.

1.  **Single elimination** supports 2 through 128 active participants. The system creates the smallest power-of-two bracket that can contain all entrants. The seeded slot order is recursive: start with `[1, 2]`; to create a bracket of size `n` from one of size `n / 2`, replace each seed `s` with `[s, n + 1 - s]`. Empty slots are byes assigned to the highest seeds. A bye is not a match and advances its participant without a score. A single-elimination result must identify one winner; draws are invalid.
2.  **Round robin** supports 2 through 32 active participants. The system generates the full circle-method schedule at tournament start. For an odd participant count, it adds a bye position so each participant has one bye; a bye counts as a win and earns 3 match points. The tournament is complete when every non-bye scheduled match is complete.
3.  **Swiss** supports 4 through 128 active participants. Before start, the admin selects from 1 through `ceil(log2(active participant count))` rounds. If the entrant count is odd, the first-round bye goes to the lowest seed. Round one pairs the seeded top half against the seeded bottom half. After every later round is complete, the system creates the next round as not ready; the admin starts it when ready.
4.  For each later Swiss round, the system first assigns a bye for an odd total participant count to the lowest-ranked participant without a prior bye, or to the lowest-ranked participant if everyone has already received one. It then pairs the remaining participants within equal match-point groups, ordered by the current standings. If a group has an odd number of participants, its lowest-ranked participant floats to the next lower group. The system avoids rematches whenever a valid pairing exists. If no no-rematch pairing is possible, it schedules the rematch whose previous meeting was earliest; seed order breaks any remaining pairing tie. A Swiss bye counts as a win and earns 3 match points, but has no opponent tiebreak value.
5.  Seeds determine single-elimination slot placement, round-robin schedule order, Swiss first-round pairings, and deterministic Swiss pairing fallbacks only. Seeds do not change match points or published final ranks.

#### Tabletop Wargames configuration

The required game system or activity identifies the tournament. MVP does not capture edition, points limit, or army size as separate fields; an admin may describe any such event rules in the required rules summary.

An admin may record each participant's optional faction and optional faction-specific rules text. These are descriptive participant details, not army or list submission, and do not affect eligibility, seeding, pairings, results, standings, or placements. An admin may edit either field in every state except cancelled, including after tournament completion.

Army or list submission, table assignment, missions, scenarios, deployment maps, round packets, round start or end times, round timers, and late-arrival handling are not MVP features. Admins start rounds manually. The tournament start date remains required, but does not create a per-round schedule or timer.

#### Standings and tiebreakers

Round-robin and Swiss standings rank participants first by match points. Before start, an admin must select one or more ordered tiebreakers; the default order is match wins, Buchholz, then head-to-head. The available MVP tiebreakers are:

1.  **Match wins** — the participant with more wins ranks higher.
2.  **Buchholz** — the sum of match points earned by opponents the participant actually played. Byes are excluded.
3.  **Head-to-head** — applies only to a two-participant tie where the participants played each other; the match winner ranks higher. It is skipped for a draw, no meeting, or a tie involving more than two participants.

Buchholz is the only MVP strength-of-schedule metric. Opponent win percentage, victory-point differential, and other game-specific tiebreakers are later scope. The configured order, each applicable value, and an explanation of the resulting rank are visible in standings. Scoring, the selected tiebreakers, and their order lock at tournament start. If final standings remain tied after all selected tiebreakers, the participants share the placement. Seed order may make a future Swiss pairing deterministic but never breaks a published standings tie.

#### Registration rules

An admin publishes a draft into registration open or registration closed. Registration requires only a display name; faction and faction-specific rules text are optional admin-managed participant details. Registration must be closed to start the tournament. Once in progress, joining is open for pending-placement requests only; an admin must confirm controlled reflow before an entrant is active. Private registration, registration deadlines, participant limits, waitlists, custom participant fields, check-in, region restrictions, and admin approval rules are later-scope items that need separate clarification.

#### Match lifecycle

MVP matches use only the following states:

1.  **Not ready** — the match belongs to a round that the admin has not started.
2.  **Active** — the admin has started the match's round; an assigned participant or admin may report a valid result.
3.  **Completed** — a valid result has been saved. Assigned participants cannot edit it; an admin may replace its result only through the completed-match correction flow.

Tournament start creates the final bracket or schedule and starts round one. The admin starts every subsequent round after its prerequisites are complete. Starting a round changes its matches from not ready to active. Saving a valid result changes an active match to completed, advances bracket entrants when applicable, and immediately updates standings. Ready, ready for score reporting, in progress, awaiting score, score submitted, under review, forfeited, and disputed are not MVP match states.

#### Completed match corrections

In every non-cancelled tournament state, including after completion, an admin may replace a completed match's valid result. The system must show the effect on standings, final placements, and unfinished competition and require confirmation before saving the correction.

The correction is blocked if it would change the entrant, opponent, or pairing of a completed downstream match. For single elimination, downstream means a later bracket match that receives its entrant from the corrected match. For Swiss, it includes a completed later-round pairing that would differ after recalculating standings and pairings. Round-robin schedules are fixed, so a corrected result only recalculates standings. When a valid correction is confirmed, the match remains completed, affected standings and final placements recalculate, and only affected not-ready or active competition reflows.

#### Admin operations and overrides

During an in-progress tournament, the only MVP change to competitive participants is controlled late placement. The admin chooses the entrant's placement and confirms a preview of changes to unfinished pairings and standings. Completed match results may be corrected only through the constrained completed-match correction flow. Faction and faction-specific rules text are descriptive participant metadata: an admin may edit them without reflow in every state except cancelled, including after completion. Format, format structure, scoring model, standings points, tiebreaker order, seed order, and bracket or schedule rules lock at start. Description, rules summary, and the tournament scheduled date/time remain editable while in progress. Completed tournaments are immutable except for participant faction metadata and completed-match corrections; cancelled tournaments are fully immutable.

#### Tournament lifecycle

MVP tournament states and transitions are:

1.  **Draft** — private to its admin. A draft may be published as registration open or registration closed, or cancelled.
2.  **Registration open** — public and joinable. The admin may close or reopen registration, or cancel the tournament.
3.  **Registration closed** — public but not joinable. The admin may reopen registration, start a valid tournament, or cancel it.
4.  **In progress** — public. Starting it starts round one. Public joins become pending placement; only confirmed controlled reflow makes them active entrants. The admin may start later rounds, complete the tournament when every required match is complete, or cancel it.
5.  **Completed** — public and final. It has no outgoing transitions. Participant faction and faction-specific rules text remain editable by an admin, and completed matches remain eligible for constrained result correction; all other tournament data is immutable.
6.  **Cancelled** — terminal and read-only. A cancelled draft remains private; a previously published tournament remains publicly viewable.

`Paused` and `Reopened` are not tournament states. `Cancelled` is the only additional MVP terminal state.
