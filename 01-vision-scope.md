# Tournament Management System — Product Document Pack

## 1. Vision + Scope

### Product vision

Create a tournament management platform that allows admins to create, manage, run, and publish tournaments for Tabletop Wargames.

The system should make tournament hosting simple for small community admins while still supporting structured, multi-stage competitive events with full control of all aspects of the tournament.

### Core problem

Existing tournament systems often automate the bracket but do not give admins enough practical control when real-world tournament problems happen. BracketFlow should help admins recover from mistakes, unexpected participant changes, incorrect scores, and operational issues without forcing them to abandon the tournament or move the event into spreadsheets.

### Product goal

The system should help admins run and administrate tournaments with the ability to control and adjust key tournament aspects, games, and participants during tournament operations.

Admin authority should be a deliberate product strength. BracketFlow should prioritize controlled admin decisions over rigid automated workflows, while still making important changes visible and requiring confirmation when changes affect brackets, standings, or final results.

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

4.  Participant joining and withdrawal.

5.  Manual participant entry by admin.

6.  Bulk participant entry by admin.

7.  Participant editing and removal by admin before tournament start.

8.  Bracket generation and preview.

9.  Manual seeding and shuffled seeding.

10. Score reporting by admins.

11. Standings, rankings, and tiebreakers.

12. Tournament completion and final results publishing.

#### Later scope

1.  Private tournament pages and private registration.

2.  Participant invitations.

3.  Custom registration questions.

4.  Check-in before tournament start.

5.  Participant score reporting.

6.  Match proof, score disputes, and result review workflows.

7.  Substitution, forfeit handling, and after-start participant changes.

8.  Two-stage tournaments, such as group stage to finals.

9.  Group assignment and advancement rules for two-stage tournaments.

10. Leaderboard and other additional tournament formats.

11. Ranking-based seeding.

12. Tournament completion reopening and broader correction workflows.

13. Tournament templates for repeated events.

#### Explicitly unresolved

1.  Detailed rules for correcting previous games, results, and participants in games. (TBD)

2.  Adding new participants after tournament start. (TBD)

3.  Adding new games after tournament start. (TBD)

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
- Participants can join, withdraw, find published tournament information, and understand whether they are currently joined or withdrawn.
- Admins can manage participant entries, seeding, score reporting, match progress, and final standings.
- Spectators can view public tournament pages, brackets, standings, match results, and final results without registering.
- The MVP avoids unsupported operational workflows and clearly identifies later-scope questions before implementation.

### Product principles

1.  Admin control: Admins must be able to manage tournament setup, participants, seeding, scores, match progress, and final results, with controlled override and recovery tools for real-world tournament issues.
2.  **Participant clarity:** Participants must always know whether they are joined, withdrawn, active, eliminated, waiting, or finished.
3.  **Result transparency:** Brackets, scores, standings, and tiebreakers should be visible and understandable.
4.  **Flexible formats:** Different competitions require different tournament formats.
5.  No hidden assumptions: Rules, advancement logic, scoring, and tiebreakers should be shown clearly to admins before the tournament starts.
6.  Controlled overrides: Admins should be able to correct and adjust an ongoing tournament when needed, but major changes should not silently rewrite history or hide corrections from affected viewers.
