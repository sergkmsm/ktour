# Tournament Management System — Product Document Pack

## 6. Open Questions and Problems

This file tracks unresolved product questions and requirement gaps that should not be treated as finalized MVP behavior until they are answered in the source documents.

### Release scope checks

1.  Private tournaments and private registration are later scope. Define whether private events are hidden by URL, invitation, account access, or another access model.
2.  Two-stage tournaments are later scope. Define how group stages, final stages, advancement, and standings interact before adding them to implementation scope.
3.  Check-in, proof, disputes, substitutions, forfeits, announcements, messaging, print/share, and broader admin overrides are later scope unless explicitly moved. Direct participant score reporting, controlled late participant placement, and tournament cancellation are MVP. Tournament reopening is not supported.

### Resolved MVP lifecycle

Tournament states are `Draft`, `Registration Open`, `Registration Closed`, `In Progress`, `Completed`, and `Cancelled`.

1.  A draft is private and may be published as registration open or registration closed, or cancelled.
2.  Registration open and registration closed are public states; the admin may move between them before start.
3.  Starting requires registration closed, valid required and format setup, valid seeding, and enough eligible participants. It creates the final bracket or schedule, changes the tournament to in progress, and starts round one.
4.  In progress is public. Participants may join with pending-placement status. An admin may place them only through confirmed controlled reflow that changes unfinished competition and preserves completed history.
5.  Completion requires every required match and round to be complete and standings and placements to calculate successfully. Completed is immutable and has no outgoing transition.
6.  An admin may cancel any nonterminal tournament after confirmation. Cancelled is terminal and read-only. A cancelled draft remains private; an already published tournament remains public.
7.  `Paused` and `Reopened` are not MVP tournament states.

MVP match states are `Not Ready`, `Active`, and `Completed`.

1.  A match is not ready until the admin starts its round.
2.  Starting a round makes its matches active. Tournament start starts round one; the admin starts every later round after its prerequisites are complete.
3.  An assigned participant or admin may submit a valid score for an active match. Saving it atomically completes the match, advances bracket entrants when applicable, and updates standings.
4.  Completed matches cannot be changed. `Ready`, `Ready for Score Reporting`, `In Progress`, `Awaiting Score`, `Score Submitted`, `Under Review`, `Disputed`, and `Forfeited` are not MVP match states.

Before start, affected setup changes automatically regenerate the current admin-only preview without retaining preview history. At start, format, structure, scoring, standings points, tiebreakers, seeds, and bracket or schedule rules lock. Description, rules summary, and scheduled date/time remain editable during in-progress play.

### Acceptance criteria precision

1.  Define what counts as required basic tournament information for AC-1 and AC-2.
2.  Define what viewers should see when match information changes in AC-43, including whether updates are real-time or refresh-based.

### Tabletop Wargames domain requirements

1.  Decide which game-system fields are MVP, such as game system, edition, points limit, army size, faction, or list submission.
2.  Decide whether army or list submission is required, optional, or later scope.
3.  Decide whether table assignment is part of MVP match operations.
4.  Decide whether missions, scenarios, deployment maps, or round packets need structured fields.
5.  Decide whether round timers, scheduled round start/end times, and late-arrival handling are supported.

### Participant and registration behavior

1.  Define whether MVP participant joining requires only display name or additional required fields.
2.  Define whether admin approval, rejection, waitlists, registration limits, and registration deadlines are MVP or later scope beyond the basic MVP joining controls.
3.  Define whether participants need accounts in MVP or can join with lightweight public information.
4.  Define how duplicate participant names are detected or handled.
5.  Define the lifecycle and visibility differences between an admin-removed participant and a participant who withdrew, including whether either can rejoin and how either appears in previews and public lists.
6.  Define how an admin-added or bulk-added offline participant is associated with a later participant identity, and who may withdraw that entry.
7.  Define the bulk participant input format, validation and normalization rules, duplicate handling, error feedback, and whether a partly invalid import is applied or rejected.

### Roles and authorization behavior

1.  Define how the system determines which identity owns a tournament and may perform admin actions; authentication implementation can remain out of scope, but authorization outcomes cannot.
2.  Define whether a tournament can have multiple admins, how ownership is transferred, and whether an admin may also join and compete in the tournament.

### Admin controls and corrections

1.  Define the format-specific placement and reflow rules for an after-start entrant, including available slots, byes, and required pairing regeneration.
2.  Define whether controlled late placement needs a retained audit/history record in addition to its required impact preview and confirmation.
3.  Define after-start participant changes other than late additions, including drops, substitutions, removals, and byes.
4.  Define the guardrails for broader future admin overrides, which must not alter MVP completed-match or completed-tournament history.

### Final results and placements

1.  Define which final placements must be published for each MVP format, including whether single-elimination semifinalists share third place when placement matches are later scope.

### Notifications and communication

1.  Decide whether MVP has any notifications, or whether participants and spectators must manually view the public tournament page.
2.  Define later-scope notifications for bracket finalization, match readiness, score changes, corrections, elimination, standings changes, and final results.
3.  Define whether announcements and participant messages require accounts, email, SMS, app notifications, or only on-page display.

### Spectator visibility

1.  Define whether spectators can discover public tournaments through search/listing or only through direct links.
2.  Define whether spectators can follow a specific match, table, participant, or faction in later releases.
3.  Define which participant fields and statuses are public, including withdrawn, removed, pending, and preview-only entries.
