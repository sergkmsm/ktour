# Tournament Management System — Product Document Pack

## 6. Open Questions and Problems

This file tracks unresolved product questions and requirement gaps that should not be treated as finalized MVP behavior until they are answered in the source documents.

### Release scope checks

1.  Private tournaments and private registration are later scope. Define whether private events are hidden by URL, invitation, account access, or another access model.
2.  Two-stage tournaments are later scope. Define how group stages, final stages, advancement, and standings interact before adding them to implementation scope.
3.  Check-in, participant self-reporting, proof, disputes, substitutions, forfeits, announcements, messaging, print/share, reopen, controlled admin overrides, and correction workflows are later scope unless explicitly moved.

### Tournament and match states

1.  Define the exact MVP tournament states and allowed transitions.
2.  Define the exact MVP match states and allowed transitions.
3.  Clarify boundaries between similar match states such as ready, ready for score reporting, in progress, and awaiting score.
4.  Define guard rules for start, score reporting, match completion, standings update, tournament completion, cancellation, and any future reopen flow.
5.  Decide whether paused, reopened, under review, disputed, forfeited, and cancelled states exist in MVP or only in later-scope workflows.

### Acceptance criteria precision

1.  Define what counts as required basic tournament information for AC-1 and AC-2.
2.  Define format-specific setup requirements for AC-3, including single elimination, round robin, and Swiss.
3.  Define valid score fields for AC-27 and invalid score behavior for AC-28.
4.  Define the MVP tiebreaker options and order for AC-34 and AC-35.
5.  Define what viewers should see when match information changes in AC-43, including whether updates are real-time or refresh-based.

### Tabletop Wargames domain requirements

1.  Decide which game-system fields are MVP, such as game system, edition, points limit, army size, faction, or list submission.
2.  Decide whether army or list submission is required, optional, or later scope.
3.  Decide whether table assignment is part of MVP match operations.
4.  Decide whether missions, scenarios, deployment maps, or round packets need structured fields.
5.  Decide whether battle points, victory points, margin of victory, sportsmanship scores, painting scores, or composition scores are supported.
6.  Decide whether strength of schedule, opponent win percentage, victory point differential, or other wargaming tiebreakers are supported.
7.  Decide whether round timers, scheduled round start/end times, and late-arrival handling are supported.

### Participant and registration behavior

1.  Define whether MVP participant joining requires only display name or additional required fields.
2.  Define whether participants can withdraw only before start or during specific later-scope states.
3.  Define whether admin approval, rejection, waitlists, registration limits, and registration deadlines are MVP or later scope beyond the basic MVP joining controls.
4.  Define whether participants need accounts in MVP or can join with lightweight public information.
5.  Define how duplicate participant names are detected or handled.

### Admin controls and corrections

1.  Define the exact scope of admin correction powers before tournament start.
2.  Define whether admins can edit scores after a match is completed during MVP.
3.  Define whether changing a completed result recalculates downstream matches, standings, and final placements automatically or requires manual confirmation.
4.  Define audit/history visibility for corrections before adding correction workflows.
5.  Define after-start participant changes, including drops, substitutions, late additions, and byes.
6.  Define the guardrails for controlled admin overrides so admins can fix real-world issues without unrestricted editing.

### Notifications and communication

1.  Decide whether MVP has any notifications, or whether participants and spectators must manually view the public tournament page.
2.  Define later-scope notifications for bracket finalization, match readiness, score changes, corrections, elimination, standings changes, and final results.
3.  Define whether announcements and participant messages require accounts, email, SMS, app notifications, or only on-page display.

### Spectator visibility

1.  Define whether spectators can discover public tournaments through search/listing or only through direct links.
2.  Define spectator visibility for not-started, in-progress, completed, cancelled, and later-scope private tournaments.
3.  Define whether spectators can follow a specific match, table, participant, or faction in later releases.
