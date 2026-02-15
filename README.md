# Saguaros University

Saguaros University is the CyberHub learning management system. It provides structured courses, hands-on labs, and digital badges that align with Cyber Saguaros training paths and CyberHub modules.

Saguaros University is planned and not yet fully implemented. This document describes the target capabilities and the intended integration points with CyberCore.

## Goals

1. Provide a consistent onboarding path for new members
2. Offer structured curriculum for red team, blue team, and CTF fundamentals
3. Issue badges and track learning progress in a standardized way
4. Integrate learning outcomes with CyberHub modules and activities
5. Support internal events, workshops, and challenge-driven learning

## Platform Scope

Saguaros University is expected to be implemented with Moodle.

Core features include:

- Courses and learning paths
- Quizzes and assessments
- Assignments and submissions
- Completion tracking
- Digital badges and achievements
- Role-based access control for students, instructors, and admins

## Identity and Access Management

- Authentication is provided through the CyberHub identity stack and coordinated through CyberCore.
- Course roles should map to CyberCore groups and Keycloak roles where applicable.
- Enrollment policies should be enforced via CyberCore-driven workflows.

## How it Works

When a user accesses Saguaros University, CyberCore handles authorization and coordinates enrollment via n8n workflows:

1. User authenticates through the CyberHub identity stack
2. CyberCore maps the user to groups and roles
3. CyberCore n8n workflows enroll the user into appropriate courses
4. Course completion and badge events are synchronized back to CyberCore
5. CyberCore stores badge state and exposes it to other modules as needed

## Badge Model

Saguaros University uses Moodle badges as the learning-side issuance mechanism, with CyberCore acting as the system of record:

- Moodle issues course badges based on completion rules
- CyberCore records earned badges and associated metadata
- Badges can be global or module-scoped
- Badge data can be used to gate access to advanced content, labs, or Crucible lanes

## Course Areas

Initial course areas are expected to include:

1. CTF fundamentals
2. Networking fundamentals
3. IT fundamentals
4. Red team fundamentals
5. Blue team fundamentals
6. King of the Hill fundamentals
7. Tool spotlights
8. Malware development
9. Operational security and safe conduct
10. CyberHub platform onboarding

## Operational Notes

- Course content should be versioned and portable.
- Where possible, labs should link directly into CyberLabs or Crucible workflows rather than relying on manual setup.
- Access to high-risk content should be gated by role and completion requirements.

## Status

Saguaros University is planned. Deployment, course authoring, and CyberCore integration will be tracked as implementation begins.