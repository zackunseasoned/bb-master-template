html
└── head
    ├── meta (charset, viewport)
    ├── title
    └── style (all inline CSS)

body
├── div.center#top
│   ├── h1
│   ├── h2
│   ├── div.period
│   └── div.patient-bar
│
├── div.nav-panel
│   ├── a.nav-btn → patient-info
│   ├── a.nav-btn → military
│   ├── a.nav-btn → allergies
│   ├── a.nav-btn → problems
│   ├── a.nav-btn → vaccines
│   ├── a.nav-btn → vitals
│   ├── a.nav-btn → medications
│   ├── a.nav-btn → results
│   ├── a.nav-btn → past-appts
│   ├── a.nav-btn → upcoming-appointments
│   ├── a.nav-btn → secure-messaging
│   ├── a.nav-btn → notes
│   ├── a.nav-btn → social-history
│   └── a.nav-btn → account-summary
│
├── div.global-controls
│   ├── button.expand-all
│   └── button.collapse-all
│
├── section#patient-info
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#patient-info-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#military
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#military-table
│       ├── div.export-controls
│       ├── p.privacy-guard
│       └── a.nav-top-link
│
├── section#allergies
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#allergy-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#problems
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#problems-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#vaccines
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#vaccines-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#vitals
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#vitals-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#medications
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#medications-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#results
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#results-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#past-appts
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#past-appts-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#upcoming-appointments
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#upcoming-appointments-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#secure-messaging
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.local-controls (expand/collapse messages)
│       ├── div.table-container
│       │   └── table#secure-messaging-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#notes
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.local-controls (expand/collapse notes)
│       ├── div.table-container
│       │   └── table#notes-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#social-history
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#social-history-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
├── section#account-summary
│   ├── div.sec-header
│   └── div.sec-content
│       ├── div.table-container
│       │   └── table#account-summary-table
│       ├── div.export-controls
│       └── a.nav-top-link
│
└── script (all inline JS)
    ├── toggleAccordion
    ├── expandAll / collapseAll
    ├── expandNotes / collapseNotes
    ├── expandMessages / collapseMessages
    ├── toggleNoteText
    ├── openAndScroll / highlightNav / closeAllSections
    ├── sortTable
    ├── exportTableToCSV
    └── exportTableToJSON
