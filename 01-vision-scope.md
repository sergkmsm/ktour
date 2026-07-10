# Tournament Management System — Product Document Pack

## 1. Vision + Scope

### Product vision

Create a tournament management platform that allows admins to create, manage, run, and publish tournaments for Tabletop Wargames.

The system should make tournament hosting simple for small community admins while still supporting structured, multi-stage competitive events with full control of all aspects of the tournament.

### Core problem

Existing tournament systems often automate the bracket but do not give admins enough practical control when real-world tournament problems happen. BracketFlow should help admins recover from mistakes, unexpected participant changes, incorrect scores, and operational issues without forcing them to abandon the tournament or move the event into spreadsheets.

### Product goal

The system should help admins run and administrate tournaments with practical control over setup, rounds, participants, games, and results during tournament operations.

Admin authority should be a deliberate product strength. BracketFlow should prioritize controlled admin decisions over rigid automated workflows, while preserving completed history and requiring confirmation when an in-progress participant placement changes unfinished pairings or standings.

### Primary outcomes

The system should enable:

- Fast tournament creation.
- Clear participant registration and management.
- Flexible tournament formats.
- Transparent brackets, standings, and match progress.
- Accurate score reporting and result tracking.
- Public tournament pages that participants and spectators can follow.

### In scope

The system includes tournament-related features only.

#### MVP scope

1.  Tournament creation and setup for public tournaments.

2.  Tournament formats:

    - Single elimination.
    - Round robin.
    - Swiss.

3.  Public tournament pages.

4.  Participant joining, including pending placement for joins submitted after tournament start, and participant withdrawal before tournament start.

5.  Manual participant entry by admin.

6.  Bulk participant entry by admin.

7.  Participant editing and removal by admin before tournament start.

8.  Controlled placement of participants added after tournament start, affecting only unfinished competition.

9.  Bracket or schedule generation and admin-only preview.

10. Manual seeding and shuffled seeding.

11. Admin-started rounds and clear match states.

12. Score reporting by assigned participants or admins.

13. Standings, rankings, and tiebreakers.

14. Tournament cancellation.

15. Tournament completion and final results publishing.

#### Later scope

1.  Private tournament pages and private registration.

2.  Participant invitations.

3.  Custom registration questions.

4.  Check-in before tournament start.

5.  Match proof, score disputes, and result review workflows.

6.  Substitution, forfeit handling, and after-start participant removals or other changes beyond controlled late placement.

7.  Two-stage tournaments, such as group stage to finals.

8.  Group assignment and advancement rules for two-stage tournaments.

9.  Leaderboard and other additional tournament formats.

10. Ranking-based seeding.

11. Tournament templates for repeated events.

#### Explicitly unresolved

1.  Adding new games after tournament start. (TBD)

### Out of scope

The following are intentionally excluded from this document:

- Technical architecture.
- Database requirements.
- API requirements.
- Hosting and infrastructure.
- Authentication implementation.
- Code, frameworks, or deployment.
- General community features not directly tied to tournaments.

### Success metrics

The product should be considered successful if:

- An admin can create and publish a basic public tournament without external help.
- Participants can join, request placement after start, submit an active-match score, find published tournament information, and understand their current status.
- Admins can manage participant entries, controlled in-progress placement, seeding, rounds, score reporting, match progress, and final standings.
- Spectators can view public tournament pages, brackets, standings, match results, and final results without registering.
- The MVP avoids unsupported operational workflows and clearly identifies later-scope questions before implementation.

### Product principles

1.  Admin control: Admins must be able to manage tournament setup, participants, seeding, scores, match progress, and final results, with controlled override and recovery tools for real-world tournament issues.
2.  **Participant clarity:** Participants must always know whether they are joined, withdrawn, active, eliminated, waiting, or finished.
3.  **Result transparency:** Brackets, scores, standings, and tiebreakers should be visible and understandable.
4.  **Flexible formats:** Different competitions require different tournament formats.
5.  No hidden assumptions: Rules, advancement logic, scoring, and tiebreakers should be shown clearly to admins before the tournament starts.
6.  Controlled reflow: Admins may place an entrant during an ongoing tournament only after reviewing and confirming the impact on unfinished competition. Completed matches, results, and completed tournaments are immutable.
