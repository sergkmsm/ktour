# Tournament Management System — Product Document Pack

## 2. Stakeholder and User Needs Summary

### Stakeholder groups

| Stakeholder | Description                                           | Main needs                                                                                         |
|-------------|-------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| Admin | Person who creates and owns the tournament | Create, publish, configure, run, cancel, and complete public tournaments; manage participants and results. |
| Participant | Individual competitor who joins a public tournament | Join, request after-start placement, withdraw before start, report assigned match results, and understand current status. |
| Spectator | Unregistered user viewing the tournament without competing | View published tournament pages, brackets, standings, match results, and final results only. |

### MVP role boundaries

| Role | MVP permissions |
|------|-----------------|
| Admin | Create and manage public tournaments, publish them, add/manage participants and their faction details, seed brackets, start tournaments and rounds, report or correct scores, place late entrants through controlled reflow, cancel tournaments, and publish final results. |
| Participant | Join a public tournament, request placement when joining after start, withdraw before start, submit a result for an assigned active match, and view public tournament information. |
| Spectator | View public tournament information only. Spectators are unregistered users and have no tournament actions. |

### MVP user needs

| User type   | Need |
|-------------|------|
| Admin | I need to create and publish a public tournament with the right format so the event structure matches my competition. |
| Admin | I need to open or close registration so I can control when participants join before start. |
| Admin | I need to manually or bulk-add participants so I can support offline signups and existing lists. |
| Admin | I need to edit, remove, and review withdrawals before start so the final bracket stays accurate. |
| Admin | I need to record and correct a participant's optional faction and faction-specific rules text without changing competitive results. |
| Admin | I need to place an entrant who joined after start while seeing and confirming the effect on unfinished pairings and standings. |
| Admin | I need to seed participants manually or randomly and privately preview current pairings before start. |
| Admin | I need to start each round so only its matches become active. |
| Admin | I need to report scores quickly so the bracket advances without delay. |
| Admin | I need to correct a completed match result without changing completed downstream matches so that I can fix errors while preserving completed competition history. |
| Admin | I need standings and tiebreakers so winners and rankings are clear. |
| Participant | I need to join a public tournament so that I can compete. |
| Participant | I need to know when an after-start join is pending admin placement. |
| Participant | I need to withdraw before start so that the admin knows I am no longer competing. |
| Participant | I need to submit a result for my active match so tournament progress can be recorded. |
| Spectator | I need to view a public tournament page so I can follow the bracket, standings, match results, and final results. |

### Later-scope user needs

| User type | Need |
|-----------|------|
| Admin | I need private tournament access controls when private tournaments are added after MVP. |
| Admin | I need participant invitations when invite-only tournaments are added after MVP. |
| Admin | I need check-in, custom registration fields, substitutions, forfeits, disputes, proof, and broader correction workflows beyond completed-match corrections after the MVP scope is stable. |
| Admin | I need controlled ways to handle drops, substitutions, and match-state issues that cannot be resolved by the MVP controlled-placement flow. |
| Admin | I need table assignments, structured round content, and timing or late-arrival controls after MVP scope is stable. |
| Participant | I may need check-in, proof submission, and dispute participation in a later release. |

### Key pain points to solve

1.  Existing tournament systems often do not give admins enough control to fix real-world event problems without leaving the system.
2.  Admins often manage brackets, participant lists, scores, and communication in separate tools.
3.  Real tournaments need manual fixes because players drop, scores are entered incorrectly, pairings need correction, tables change, and timing issues happen.
4.  Participants get confused when provisional brackets change before the tournament starts or a late entrant affects an ongoing event.
5.  Participant withdrawals and admin removals need to be visible before bracket generation, while late entrant placement must not rewrite completed history.
6.  Score reporting, bracket advancement, and standings need one source of truth.
7.  Participants and spectators need a single public page for brackets, standings, match results, and final results.
8.  Later-scope features such as private tournaments, two-stage tournaments, disputes, and forfeits need separate clarification before implementation.
