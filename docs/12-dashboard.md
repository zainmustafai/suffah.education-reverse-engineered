# Dashboard

- Route(s): /dashboard
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/dashboard/dashboard.png (batch 1)

## Layout
- Greeting: "Assalamu alaikum, MUHAMMAD" / "Here's what's happening at maddrassah today."
- Counter cards: STUDENTS | TEACHERS | ATTENDANCE TODAY | OVERDUE FAMILIES.
- Header: a "4/5 set up" link, Notifications button, account menu (MZ).
- Setup checklist "Get your school set up - N of 5 done" with a per-step Done / Go state.
- Help card: "Need a hand getting set up? Book a free call and we'll walk through it with you."
- Quick Actions (2 cards): "Teacher Timesheet - View teachers clock-in/out" and
  "Analytics - View school performance analytics".
- "Recent Activity" panel.
- Sidebar (same across admin): NAVIGATION - Dashboard, Announcements, Chat, Classroom;
  BILLING - Subscription; TOOLS - Tools; plus "Send diagnostics" and "Toggle Sidebar".

## State after the walkthrough (2026-10-31)
- STUDENTS 3 - includes the orphaned duplicate Yusuf (docs/05-users.md, flows/admit-siblings.md).
- TEACHERS 0 - WRONG: Users lists two Active teachers. The dashboard counter does not read
  the same source as Users.
- ATTENDANCE TODAY 0% - with 1 Late + 1 Absent + 0 Present marked. Consistent with a
  present-only percentage; the formula is stated nowhere in the UI. (Student Analytics,
  by contrast, counts a Late day toward its attendance rate - see docs/17-student-analytics.md.
  The two surfaces use different definitions.)
- OVERDUE FAMILIES 0.
- Setup checklist 4 of 5: school details Done, create a program Done, assign teachers Done,
  assign students from admissions Done; only "Copy registration link - Share it so families
  can apply" still shows "Go".
- Recent Activity: "No recent activity to display" - empty even after a full day of creating
  programs, users, a family, charges and attendance (matches the Activity Log's gaps,
  docs/19-activity-log.md).
