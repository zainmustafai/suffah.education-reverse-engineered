# Suffah Education - App Overview

Mapped live on 2026-10-31 from a signed-in session (mapping only - nothing created, edited, or deleted).
Product: Suffah School Management (suffah.education) - management software for Quran schools / madrassahs.
Companion context: the public home page markets Student Management, Teacher Management, Analytics & Reports,
Communication Hub, Academic Calendar, Subject Management, Attendance Tracking, and Foundation Config.
Only the in-app items below are confirmed from inside the product.

## Account used for the walkthrough
- Signed-in user: MUHAMMAD ZAIN UL ABIDIN, role "Manager" (profile menu avatar "MZ").
- School name as shown on the dashboard: "maddrassah".
- Dashboard greeting: "Assalamu alaikum, MUHAMMAD" - "Here's what's happening at maddrassah today".
- Fresh account state: Students 0, Teachers 0, Attendance Today 0%, Overdue Families 0, "No recent activity to display."
- Setup checklist "Get your school set up - 3 of 5 done": school details, create a program, assign teachers
  are done; copy registration link and assign students from admissions are outstanding.
- Quick Actions on the dashboard: Teacher Timesheet, Analytics.
- Profile menu holds only: Profile, Toggle Theme, Log out.
  No role switching and no institute/branch switching found in the sidebar or profile menu.

## Main navigation (sidebar groups: NAVIGATION / BILLING / TOOLS)

| Module | Route | What it is |
| --- | --- | --- |
| Dashboard | /dashboard | Stats, setup checklist, Quick Actions, Recent Activity. |
| Announcements | /announcements | Broadcast to SMS, Email and in-app notification. Credit based: 200 credits shown, $0.05 per credit, "Add credits" and "Create Announcement" actions. List items carry states such as PENDING APPROVAL and PUBLISHED. |
| Chat | /chat | Messages. Search by full name or username. People / Groups tabs, All Roles and Active filters, Recent contacts, pinned "Platform Support / Unified Support" contact. |
| Classroom (sidebar label) | /attendance | Attendance taking: "Select Class / Choose the class for attendance", Search classes, All classes / Step-by-step modes. NOTE: the sidebar label "Classroom" links to /attendance. The URL /classroom itself is a separate public family-portal page ("Sign in to your family portal, or register"), not the in-app page. |
| Subscription (BILLING) | /subscription | Plan "Up to 50 students", $2.50 per student/month, status Active, 0/50 used. $125.00 less 2.5% tier discount ($3.13) = $121.88 due monthly. Actions: View plans, Manage billing, Pay (Pay not clicked - mapping only). Plan includes unlimited teachers and classes, Attendance, Chat & Announcements, Programs, Admissions & Finance tools, priority email support. |
| Tools | /tools | Searchable hub of all tools below. Each card has a "Pin to top" action. |
| Profile (via avatar menu) | /profile | Personal information and account settings, with Edit and Change Password controls. |

Other chrome: "3/5 set up" link, Notifications button, Toggle Sidebar button,
and a "Send diagnostics" button at the bottom of the sidebar.

## Tools hub (/tools) - grouped as shown in the app

### SCHOOL
| Tool | Route | Notes |
| --- | --- | --- |
| School Settings | /school-settings | Main settings area. Tabs: School Info, Roles, Holidays. (Save was disabled during mapping and not used.) |
| Programs | /tools/programs | |
| Admissions | /tools/registration | Registration / admissions intake. |
| School Page | /tools/school-page | |
| Hours | /tools/hours | |

### PEOPLE & MONEY
| Tool | Route | Notes |
| --- | --- | --- |
| Users | /users | |
| Families | /tools/families | |
| Special Care | /users?role=Student&specialCare=1 | Filtered Users view. |
| Finance | /tools/finance | |

### TEACHING
| Tool | Route | Notes |
| --- | --- | --- |
| Learning Pathway | /tools/learning-pathway | |
| Course Tool | /tools/course | Marked "In development" in the hub. |
| Interactive Qur'an | /tools/interactive-quran | Marked "In development" in the hub. |

### INSIGHT
| Tool | Route | Notes |
| --- | --- | --- |
| Student Analytics and History | /tools/student-analytics | |
| Reports | /tools/reports | |

### RECORDS (shown "In development", disabled, no link)
- Forms
- Handbooks
- Secure Files

### SAFEKEEPING
| Tool | Route | Notes |
| --- | --- | --- |
| Activity Log | /tools/activity | |
| Backups | /tools/backups | |

## Screenshot / viewport note
Screenshots from this mapping pass render in a wide desktop layout (full sidebar, multi-column content).
The browser used for the pass offered no window-resize control and no viewport-size readout, so an exact
1920x1080 capture size is NOT verified for this pass. One early sidebar toggle rendered as a mobile-style
dialog. Per-module walkthrough captures must be checked against the desktop-view requirement as they are taken.
