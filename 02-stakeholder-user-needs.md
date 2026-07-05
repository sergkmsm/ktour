# Tournament Management System — Product Document Pack

## 2. Stakeholder and User Needs Summary

### Stakeholder groups

| Stakeholder | Description                                           | Main needs                                                                                         |
|-------------|-------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| Admin       | Person who creates and owns the tournament            | Create public tournaments, manage participants, configure format, start/end tournament, report results |
| Participant | Individual competitor who joins a public tournament   | Join, withdraw, view public tournament information, and understand current join status              |
| Spectator   | Unregistered user viewing the tournament without competing | View public tournament pages, brackets, standings, match results, and final results only            |

### MVP role boundaries

| Role | MVP permissions |
|------|-----------------|
| Admin | Create and manage public tournaments, add/manage participants, seed brackets, start tournaments, report scores, advance matches, and publish final results. |
| Participant | Join a public tournament, withdraw from a joined tournament, and view public tournament information. |
| Spectator | View public tournament information only. Spectators are unregistered users and have no tournament actions. |

### MVP user needs

| User type   | Need                                                                                                            |
|-------------|-----------------------------------------------------------------------------------------------------------------|
| Admin       | I need to create a public tournament with the right format so the event structure matches my competition.       |
| Admin       | I need to open joining so participants can add themselves to the tournament.                                    |
| Admin       | I need to manually add participants so I can support offline signups.                                           |
| Admin       | I need to bulk-add participants so I can quickly set up tournaments from an existing list.                      |
| Admin       | I need to edit or remove participants before start so the bracket stays accurate.                               |
| Admin       | I need to see participant withdrawals so I can make final bracket decisions.                                    |
| Admin       | I need to seed participants manually or randomly so matchups are ready before start.                            |
| Admin       | I need to preview the bracket before finalizing so participants do not assume early pairings are final.         |
| Admin       | I need to report scores quickly so the bracket advances without delay.                                          |
| Admin       | I need standings and tiebreakers so winners and rankings are clear.                                             |
| Participant | I need to join a public tournament so that I can compete.                                                       |
| Participant | I need to withdraw from a tournament so that the admin knows I am no longer competing.                          |
| Participant | I need to know whether I am joined or withdrawn.                                                               |
| Spectator   | I need to view a public tournament page so I can follow the bracket, standings, match results, and final results. |

### Later-scope user needs

| User type   | Need                                                                                                           |
|-------------|----------------------------------------------------------------------------------------------------------------|
| Admin       | I need private tournament access controls when private tournaments are added after MVP.                         |
| Admin       | I need participant invitations when invite-only tournaments are added after MVP.                                |
| Admin       | I need check-in, custom registration fields, substitutions, forfeits, disputes, proof, and correction workflows after the MVP scope is stable. |
| Participant | I may need check-in, score self-reporting, proof submission, and dispute participation in a later release.      |

### Key pain points to solve

1.  Admins often manage brackets, participant lists, scores, and communication in separate tools.
2.  Participants get confused when brackets change before the tournament starts.
3.  Participant withdrawals and admin removals need to be visible before bracket generation.
4.  Score reporting, bracket advancement, and standings need one source of truth.
5.  Participants and spectators need a single public page for brackets, standings, match results, and final results.
6.  Later-scope features such as private tournaments, two-stage tournaments, disputes, and corrections need separate clarification before implementation.
