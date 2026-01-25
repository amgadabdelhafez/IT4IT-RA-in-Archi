# CLAUDE.md - AI Assistant Guide for IT4IT-RA-in-Archi

## Project Overview

This repository contains the **IT4IT Reference Architecture** modeled in the **ArchiMate** enterprise architecture modeling language using the **Archi** tool.

### What is IT4IT?

IT4IT is an Open Group standard that prescribes holistic management of the business of IT with continuous insight and control. It provides:
- A reference architecture and value chain-based operating model for managing IT
- Prescriptive guidance on designing, procuring, and implementing IT functionality
- End-to-end tracking of service states across the service lifecycle
- Boundaryless Information Flow across the entire IT Value Chain

### What is ArchiMate?

ArchiMate is an open and independent enterprise architecture modeling language that:
- Supports description, analysis, and visualization of architecture
- Works within and across business domains
- Is fully aligned with TOGAF (The Open Group Architecture Framework)

### What is Archi?

Archi is a free, open-source, cross-platform tool for creating ArchiMate models. The `.archimate` files in this repository are XML-based model files created and edited with Archi.

## Repository Structure

```
IT4IT-RA-in-Archi/
├── IT4IT_Reference_Architecture-V0.1.archimate    # Initial model version
├── IT4IT_Reference_Architecture-V0.1.archimate.bak
├── IT4IT_Reference_Architecture-V0.2.archimate    # Second iteration
├── IT4IT_Reference_Architecture-V0.2.archimate.bak
├── IT4IT_Reference_Architecture-V0.3.archimate    # Third iteration
├── IT4IT_Reference_Architecture-V0.3.archimate.bak
├── IT4IT_Reference_Architecture-V0.4.archimate    # Updated to IT4IT 3.0 terminology
├── IT4IT_Reference_Architecture-V0.4.archimate.bak
├── IT4IT_Reference_Architecture-V0.5.archimate    # Current/latest - IT4IT 3.0 aligned
├── README.md                                       # Project documentation
├── CLAUDE.md                                       # This file
├── IT4IT/                                          # Additional model files
├── PDFs/                                           # Reference documentation, course materials
└── images/                                         # Diagrams and reference images
```

## File Types and Formats

| Extension | Description | How to Work With |
|-----------|-------------|------------------|
| `.archimate` | ArchiMate model files (XML format) | Edit with Archi tool; can read as XML |
| `.archimate.bak` | Backup files created by Archi | Automatic backups, not for direct editing |
| `.pdf` | Reference documentation | Read-only reference materials |
| `.png`, `.jpg`, `.bmp`, `.svg` | Diagram images | Visual references and exports |
| `.md` | Markdown documentation | Edit directly |

## ArchiMate Model Structure

The `.archimate` files are XML documents with the following structure:

```xml
<archimate:model xmlns:archimate="http://www.archimatetool.com/archimate"
                 name="Model Name" id="unique-id" version="4.0.0">
    <!-- Standard folder organization -->
    <folder name="Business" type="business"/>
    <folder name="Application" type="application">
        <!-- Application Components, Interfaces, Data Objects -->
    </folder>
    <folder name="Technology" type="technology"/>
    <folder name="Motivation" type="motivation"/>
    <folder name="Implementation &amp; Migration" type="implementation_migration"/>
    <folder name="Connectors" type="connectors"/>
    <folder name="Relations" type="relations">
        <!-- Relationships between elements -->
    </folder>
</archimate:model>
```

### Key Element Types

- **ApplicationComponent**: Software components (e.g., `ServiceNow`, `Portfolio Demand Component`)
- **ApplicationInterface**: Interfaces between components (e.g., `ServiceNow Catalog API`)
- **DataObject**: Data entities (e.g., `Users`, `Service Architecture`, `Stages`)
- **AssociationRelationship**: Connections between elements

### Element ID Format

Elements use hexadecimal UUID identifiers (e.g., `id="6a18db2b"`).

## Naming Conventions

### File Naming
- Model files: `IT4IT_Reference_Architecture-V[version].archimate`
- Use snake_case with underscores for spaces
- Version format: `V0.X` (e.g., V0.1, V0.2, V0.3, V0.4)

### ArchiMate Element Naming
- **Application Components**: PascalCase, often with descriptive suffix (e.g., `Enterprise Architecture Component`)
- **Data Objects**: PascalCase (e.g., `Service Architecture`)
- **Interfaces**: Descriptive with API/Interface suffix (e.g., `ServiceNow Catalog API`)

## Key Components in the Model

The IT4IT Reference Architecture model (V0.5, aligned with IT4IT 3.0) includes:

| Category | Components |
|----------|------------|
| **Strategy** | Strategy Component (new in 3.0), Policy Component |
| **Product Management** | Product Portfolio Component, Product Vision, Product Design |
| **User Management** | Users Controller, User Wallet, Request Management |
| **Architecture** | Enterprise Architecture Component, Product Architecture |
| **Development** | Build Component, Test Component, Defect Component, Source Control |
| **Operations** | Release Composition, Configuration Management, Product Monitoring |
| **Support** | Problem Component, Incident Component, Product Level Component |

### IT4IT 3.0 Value Streams

The model now reflects the 7 value streams introduced in IT4IT 3.0:
- **Evaluate** - Assess and optimize the Product Portfolio
- **Explore** - Explore new features and product directions
- **Integrate** - Design and build new Product Releases
- **Deploy** - Deploy releases to environments
- **Release** - Release products to market/business
- **Consume** - Enable consumption of products
- **Operate** - Monitor and address production issues

## Development Workflow

### This is NOT a Traditional Software Project

This repository contains enterprise architecture models, not code. There is:
- No build system or compilation
- No package management (npm, pip, etc.)
- No CI/CD pipelines
- No automated testing

### Working with Model Files

1. **Viewing**: Open `.archimate` files in Archi tool, or read as XML
2. **Editing**: Use Archi tool (recommended) for visual editing
3. **XML Editing**: Direct XML editing is possible but risky - maintain valid structure
4. **Backups**: Archi creates `.bak` files automatically

### Version Control Practices

- **Commit Messages**: Keep descriptive but concise
- **Versioning**: Increment version number when creating new model iterations
- **Backups**: Commit `.bak` files alongside main model files
- **Large Files**: Images and PDFs are tracked in git (repository is ~43MB)

## Guidelines for AI Assistants

### DO

1. **Read model files as XML** when asked about architecture content
2. **Parse element names and relationships** to understand the model structure
3. **Reference PDFs and images** as documentation sources
4. **Use the latest version** (V0.5) as the current state
5. **Preserve XML structure** when making any edits

### DON'T

1. **Don't break XML validity** - always maintain proper structure
2. **Don't change element IDs** - they are used for relationships
3. **Don't remove .bak files** - they serve as backups
4. **Don't assume code patterns** - this is architecture modeling, not programming

### When Analyzing the Model

To understand the architecture:
1. Read the latest `.archimate` file (currently V0.4)
2. Look for `<element>` tags to find components
3. Look for `<element ... xsi:type="archimate:AssociationRelationship">` for relationships
4. The `source` and `target` attributes reference element IDs

Example query to find all Application Components:
```bash
grep -o 'xsi:type="archimate:ApplicationComponent"[^>]*name="[^"]*"' IT4IT_Reference_Architecture-V0.5.archimate
```

## External Resources

- **IT4IT Official**: http://www.opengroup.org/IT4IT/overview
- **ArchiMate**: http://www.opengroup.org/subjectareas/enterprise/archimate-overview
- **Archi Tool**: http://www.archimatetool.com

## Repository Metadata

- **Primary Language**: ArchiMate (XML-based)
- **Tool Required**: Archi (for visual editing)
- **Total Size**: ~43MB (includes images and PDFs)
- **Current Model Version**: V0.5 (aligned with IT4IT 3.0)
- **IT4IT Standard Version**: 3.0
- **No License File**: Licensing status unclear

---

*Last updated: 2026-01-25*
