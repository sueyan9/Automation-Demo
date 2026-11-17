# Clinic Appointment Automation – UiPath Project Guide

2026-11-17

## Goal and scope

Project 01 is a small UiPath automation that reads patient appointments from Excel, emails confirmations, and records Sent or Failed back in the file. The goal is twofold: learn UiPath step by step, and build something reusable that can later plug into the TCM system.

We build it incrementally: one small feature at a time, understand why it is designed that way, then test it before moving on.

## Design principles

Start simple. Add structure only when a real need appears.

- **No REFramework for now.** REFramework suits enterprise processes with many transactions, retries, exception classification and Orchestrator integration. A small learning project does not need it.
- **Windows / Modern for the first exercise.** Cross-platform and Windows are not just different runtimes: some activities and UI Automation capabilities differ between them.
- **No Common/, Library or Project Template yet.** Extract shared logic only after the same logic appears in more than one place.
- **Excel + Email first.** Web automation comes later, once the basics are solid.

## Project 01: Clinic Appointment Automation

Data flows through four steps:

1. **Input:** Appointments.xlsx holds the patient appointment data.
2. **UiPath Studio:** reads the file, filters rows, and loops over them.
3. **Email automation:** sends an appointment confirmation email for each row.
4. **Output:** the updated Excel file records Sent or Failed per row.

## Six development stages

Finish each stage before starting the next.

| Stage | Content | Learning focus |
| --- | --- | --- |
| 1 | Create the project and file structure | Studio, Workflow |
| 2 | Create Excel test data | Excel Activities |
| 3 | Read the Excel file | DataTable, Variables |
| 4 | Filter Confirmed appointments | If, For Each Row |
| 5 | Send emails | Email Integration |
| 6 | Exception handling and logging | Try Catch, Logging |

## Step 1: Create the project

In UiPath Studio:

1. Click **New Project**.
2. Choose **Process**.
3. Name it `ClinicAppointmentAutomation`.
4. Set Compatibility to **Windows**.
5. Set Design Experience to **Modern** (if the option is shown).
6. Click **Create**.

Do not choose REFramework.

## Step 2: Folder structure

Start with only what the first version needs:

```
ClinicAppointmentAutomation/
├── Main.xaml
├── Data/
│   ├── Input/
│   │   └── Appointments.xlsx
│   └── Output/
├── Process/
│   └── Send_Appointment_Email.xaml
└── README.md
```

Framework/, Common/, Objects/ and Tests/ are left out on purpose. Add them when a real need appears.

## Current task

Do only the first step now, not everything at once.

- [ ] Open UiPath Studio
- [ ] Select New Project, then Process
- [ ] Enter the name ClinicAppointmentAutomation
- [ ] Select Windows and Modern
- [ ] Reach the Studio workspace

When done, send a screenshot of the Studio main screen.

**Next:** create the Excel test data, with an explanation of each UiPath activity, its variable types and how it connects. Each session adds one small feature, explains why it is designed that way, and you build and test it yourself. At the end we combine the small workflows into a reusable automation framework.
