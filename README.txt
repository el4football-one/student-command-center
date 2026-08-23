STUDENT COMMAND CENTER — v1.0 RELEASE CANDIDATE
ProgressMint Studios

RELEASE-CANDIDATE ADDITIONS
• Four-step first-run student onboarding
• PWA readiness diagnostics in Settings
• Secure-hosting / manifest / service-worker / storage status
• Service-worker update-ready messaging
• Existing Help Center retained for ongoing how-to support
• Existing academic, extracurricular, parent-share, accessibility, responsive,
  personalization, backup and data-integrity features retained

VERIFIED IN STATIC QA
The package structure and required feature hooks are present.

NOT YET VERIFIED / NOT FOR MARKETING CLAIMS YET
• Physical iPhone, iPad, Android phone/tablet and Chromebook testing
• Hosted HTTPS install flow
• Full offline behavior after hosted first load
• Screen-reader testing
• Cross-device synchronization
• Automatic parent emails
• Background push notifications

RELEASE GATE
Deploy to HTTPS staging, then execute the real-device/browser test matrix before packaging the Etsy buyer release.


SECURITY & PRIVACY RELEASE-CANDIDATE PASS
• Local-first privacy explanation
• No ad / behavioral-tracking scripts in packaged build
• Content Security Policy restricts external resources/network connections
• Privacy audit surfaces locally stored parent email/activity-location categories
• Double-confirmed Delete My Planner Data control
• Guidance discourages precise home/personal locations and unnecessary sensitive data
• Parent sharing remains student-previewed and non-automatic

SECURITY LIMITATION
Browser localStorage is NOT encrypted secure storage and should not be described that way.
OWASP recommends avoiding sensitive information in localStorage where authentication/security is assumed.
For any future accounts/cloud sync, move sensitive data to an appropriately secured backend, use HTTPS,
secure authentication/session handling, encryption, access controls, retention/deletion controls, and formal security review.

CHILDREN'S PRIVACY RELEASE GATE
If the hosted service collects personal information from children under 13 and COPPA applies, launch must
not proceed until the applicable notice, verifiable parental consent, parental access/deletion, security,
data-minimization, retention/deletion, and related requirements are properly addressed and reviewed.


PRIVACY HARDENING PASS
• Privacy-first mode enabled by default
• Parent email is session-only by default instead of persistent localStorage
• General-location validation blocks address/ZIP/coordinate-looking activity locations in privacy mode
• Referrer policy set to no-referrer
• Existing CSP, data deletion, privacy audit, backup validation, and no-tracker package design retained

This reduces personal information persisted locally. It does not make localStorage encrypted secure storage
and is not a security certification.


RELEASE-GATE PASS
• In-app Release Safety Gate distinguishes implemented safeguards from unverified launch requirements
• Privacy-safe backup strips parent email and activity locations
• Buyer-ready status explicitly remains blocked pending HTTPS staging, real-device QA,
  accessibility QA, and child-privacy/legal review if applicable
• Privacy-first mode, CSP, no-referrer, deletion controls, and local storage checks remain intact

IMPORTANT
This build is a release candidate, not a security certification or legal-compliance certification.
If a future hosted service collects personal information from children under 13, determine whether COPPA
applies before collection. Current FTC guidance includes parental notice/consent, parental access/deletion,
reasonable security, data minimization, and retention/deletion obligations for covered operators.


REAL-DEVICE QA CORRECTION PASS
• Mobile Weekly View: vertical 7-day agenda.
• 12-hour AM/PM display throughout schedule-facing UI.
• Explicit high-contrast AM/PM selectors for activity entry.
• Main mobile nav standardized to Assignments.
• Job / Work Shift supported in Schedule.
• Persistent global Help control.
• Help search results appear directly below search.
• First-time setup/Quick Start moved to reference position after onboarding.
• Parent Updates renamed and made more prominent.
• Last active screen persists across return/reload.
• Study screen/session goal/timer running/paused state persist.

RETEST REQUIRED on HTTPS staging for all corrected behaviors.


FINAL STUDY MODE CORRECTION
• 25 minutes remains the recommended default, not the only option.
• Presets: 10, 15, 25, 30, 45, 60 minutes.
• Custom duration: 5–120 minutes.
• XP is awarded only when a focus session completes and is capped:
  5–15 min = 10 XP; 16–30 min = 25 XP; 31–45 min = 35 XP; 46–120 min = 40 XP.
• Recent completed sessions show duration, session goal, date, and XP.
• Pause/Resume, background timing, session goal persistence, and last-screen persistence remain.


NAVIGATION HOTFIX + ACTIVITY EDITING
• Fixed a JavaScript syntax defect that prevented bottom navigation and other controls from responding.
• Added Edit Activity support for saved schedule items.
• Edit pre-fills title, category, date, 12-hour start/end time, location, recurrence, custom days and notes.
• Save Changes updates the existing item instead of recreating it.
• Delete Activity remains available with Undo protection.
• Existing mobile weekly agenda, 12-hour formatting, adjustable Study timer, Help, Parent Updates and state persistence retained.


TIMER + MOBILE MODAL HOTFIX
• Running Study sessions now reconcile from an absolute end time when the app returns to foreground.
• Paused sessions remain paused and show Resume.
• Pause is shown only while the timer is actively running.
• Schedule activity modal has extra mobile bottom spacing so Save/Delete buttons stay above the fixed nav.


HELP + BACK + MODAL HOTFIX
• Floating Help button is now visible on every main screen and hidden only while Help is open.
• Browser/system Back now steps through Student Command Center screen history before leaving the site.
• Schedule activity Save/Delete controls use a sticky mobile action bar above the fixed bottom navigation.
• Extra safe-area spacing protects controls from browser/device bottom chrome.


STABILITY HOTFIX
• An active or paused Study session now takes priority on app re-entry and restores directly to Study.
• Browser history initializes to the restored screen instead of Dashboard.
• The fixed mobile bottom navigation and floating Help control are hidden while Add/Edit Activity is open, eliminating tap interception and button overlap.
• Save/Delete activity actions remain fully visible in normal modal flow.


GLOBAL HELP PERSISTENCE HOTFIX
• Floating Help remains available on every main screen.
• Help is hidden only while the Help screen itself is open.
• Visibility is re-synced after screen changes, app return/pageshow, and visibility changes.
• Existing Progress-section Help content remains as a secondary entry point, not the primary one.


TIME + ASSIGNMENT COMPLETION HOTFIX
• User-facing schedule/class/activity times are normalized through 12-hour AM/PM formatting.
• Assignment completion now uses a persistent checked state instead of switching the main control to Undo.
• Completed assignments remain visibly completed and can be marked incomplete by tapping the checked control again.
• Friendly assignment dates are used in the item display.
