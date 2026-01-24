# CLAUDE.md - AI Assistant Guide for IT4IT-RA-in-Archi

## Project Overview

This is an **enterprise architecture modeling project**, not a traditional software codebase. It documents the IT4IT Reference Architecture standard using the ArchiMate modeling language and the Archi tool.

### What This Project Is

- **IT4IT Reference Architecture**: An Open Group standard that prescribes holistic management of the business of IT with continuous insight and control, enabling Boundaryless Information Flow across the entire IT Value Chain
- **ArchiMate**: An open, independent enterprise architecture modeling language for describing, analyzing, and visualizing architecture within and across business domains
- **Archi Tool**: A free, open-source, cross-platform tool for creating ArchiMate models

### Key Resources

- IT4IT: http://www.opengroup.org/IT4IT/overview
- ArchiMate: http://www.opengroup.org/subjectareas/enterprise/archimate-overview
- Archi: http://www.archimatetool.com

---

## Repository Structure

```
IT4IT-RA-in-Archi/
├── README.md                                    # Project documentation
├── CLAUDE.md                                    # This file - AI assistant guide
├── IT4IT_Reference_Architecture-V0.1.archimate  # Model version 0.1
├── IT4IT_Reference_Architecture-V0.2.archimate  # Model version 0.2
├── IT4IT_Reference_Architecture-V0.3.archimate  # Model version 0.3
├── IT4IT_Reference_Architecture-V0.4.archimate  # Model version 0.4 (LATEST)
├── *.archimate.bak                              # Automatic backup files
├── PDFs/                                        # Reference documentation and standards
│   ├── Reference Architecture-V2.PDF            # Official IT4IT reference
│   ├── IT4IT-intro-Units00-Course-Overview.pdf  # Course materials
│   ├── Request to Fulfill (R2F) Value Stream.pdf
│   └── Various diagrams (PNG/JPG)
├── IT4IT/                                       # Additional reference materials
└── images/                                      # Rendered architecture diagrams
    ├── IT4IT RA L1.*                            # Level 1 Reference Architecture (multiple formats)
    ├── IT4IT Value Streams.png
    └── Activity diagrams for value streams
```

---

## Primary Artifacts

### ArchiMate Model Files (.archimate)

These are the core artifacts of this project - XML-based files that store the enterprise architecture model.

**Latest Version**: `IT4IT_Reference_Architecture-V0.4.archimate`

**File Format**: XML 1.0 documents with ArchiMate semantics

**Structure**:
```xml
<archimate:model>
  <folder name="Business">         <!-- Business architecture elements -->
  <folder name="Application">      <!-- Application components and data objects -->
  <folder name="Technology">       <!-- Technology infrastructure -->
  <folder name="Motivation">       <!-- Business drivers, goals, constraints -->
  <folder name="Implementation & Migration">
  <folder name="Connectors">
  <folder name="Relations">        <!-- All relationships stored here -->
</archimate:model>
```

### Element Types Used

| Type | Purpose | Count in V0.4 |
|------|---------|---------------|
| `archimate:ApplicationComponent` | Software services/systems | 34 |
| `archimate:DataObject` | Information/data entities | 44 |
| `archimate:AssociationRelationship` | Connections between elements | 40+ |
| `archimate:ArchimateDiagramModel` | Visual diagram containers | 2 |
| `archimate:ApplicationInterface` | User-facing interfaces | 1 |
| `canvas:CanvasModel` | Free-form annotations | 1 |

---

## IT4IT Value Streams Modeled

The architecture captures four main IT value streams:

1. **Strategy to Portfolio (S2P)** - Strategic planning and demand management
2. **Request to Fulfill (R2F)** - Service request and fulfillment processes
3. **Requirement to Deploy (R2D)** - Requirements and deployment processes
4. **Detect to Correct (D2C)** - Issue detection and resolution processes

### Key Components by Value Stream

**Demand & Portfolio Management (S2P)**:
- Portfolio Demand Component
- Service Portfolio Component
- Policy Component
- Enterprise Architecture Component

**Service Lifecycle (R2D)**:
- Requirement Component
- Project Component
- Service Design Component
- Source Control Component
- Build Component
- Test Component

**Fulfillment (R2F)**:
- Catalog Component
- Offer Management Component
- Fulfillment Execution Component
- Service Release Component

**Operations (D2C)**:
- Service Monitoring Component
- Event Component
- Incident Component
- Problem Component
- Change Control Component
- Configuration Management Component

**Integration**:
- ServiceNow (primary system of record)
- Users Controller
- User Wallet

---

## Development Workflow

### No Build System

This is a modeling project with no automated build, test, or deployment pipelines.

### Manual Workflow

1. Open `.archimate` file in Archi tool
2. Modify/add architecture elements and diagrams
3. Save (creates automatic `.bak` backup)
4. Export diagrams as images if needed
5. Commit changes to Git
6. Push to remote repository

### Required Tools

- **Archi Tool** (v3.1.1+): Required for viewing/editing `.archimate` files
- **Git**: Version control
- **Text/XML Editor**: For direct file inspection (optional)
- **PDF Reader**: For reference documentation

---

## Conventions

### File Naming

- Model files: `IT4IT_Reference_Architecture-V{Major}.{Minor}.archimate`
- Semantic versioning: V0.1, V0.2, V0.3, V0.4...
- Latest version is always the primary reference

### Element Naming

- **Components**: PascalCase with "Component" suffix (e.g., "Service Portfolio Component")
- **Data Objects**: Descriptive names (e.g., "Service Contract", "Portfolio Backlog Item")
- **IDs**: Hex format (e.g., "6a18db2b")

### Documentation Pattern

Elements can include documentation in the XML:
```xml
<element xsi:type="archimate:DataObject" id="5054a846" name="Stages">
  <documentation>{in_progress, canceled, paused, completed, breached}</documentation>
</element>
```

### Git Commit Messages

- Semantic versioning references ("version 2")
- Direct action descriptions ("adding images", "removing old files")
- Generally informal but descriptive

---

## Important Notes for AI Assistants

### What This Project IS

- An ArchiMate enterprise architecture model
- XML-based documentation of IT4IT Reference Architecture
- Visual modeling project (diagrams are outputs)

### What This Project IS NOT

- A software application to build/deploy
- Code that can be executed
- Something with dependencies to manage

### Before Making Changes

1. **Understand ArchiMate semantics** - Changes must maintain XML validity and ArchiMate language compliance
2. **Preserve relationships** - The `<folder name="Relations">` section contains critical connections
3. **Maintain version convention** - Create new version files rather than overwriting
4. **Update backups appropriately** - `.bak` files are created automatically by Archi

### Key Files for Reference

| File | Purpose |
|------|---------|
| `IT4IT_Reference_Architecture-V0.4.archimate` | Latest model version |
| `README.md` | Project overview |
| `PDFs/Reference Architecture-V2.PDF` | Official IT4IT standard |
| `images/IT4IT RA L1.svg` | Level 1 architecture diagram |

### Common Tasks

**To understand the architecture**:
- Read the latest `.archimate` file as XML
- Review diagrams in `images/` directory
- Consult PDFs for official standards

**To describe the model**:
- Parse XML structure for element counts
- Identify relationships between components
- Map to IT4IT value streams

**To modify the model** (if needed):
- Edit XML directly with care for ArchiMate semantics
- Or recommend changes for human to implement in Archi tool
- Always preserve XML schema compliance

---

## Quick Reference

```
Project Type:     Enterprise Architecture Model
Primary Format:   ArchiMate XML (.archimate)
Latest Version:   V0.4
Build System:     None
Dependencies:     None (external tool: Archi)
Main Branch:      master
```
