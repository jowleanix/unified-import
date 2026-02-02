# Inventory Builder Rebuild - Sprint Plan Q1 2025

## Quick Navigation

- [Initiative Overview](#initiative-overview)
- [Phase 1: Foundation (Weeks 1-3)](#phase-1-foundation)
- [Phase 2: Diagram Recognition (Weeks 4-5)](#phase-2-diagram-recognition)
- [Phase 3: Core Completion (Weeks 6-9)](#phase-3-core-completion)
- [Phase 4: Customer Rollout (Weeks 10-11)](#phase-4-customer-rollout)
- [Timeline Overview](#timeline-overview)
- [Critical Success Points](#critical-success-points)

---

## Title Slide

**Inventory Builder Rebuild**
11-Step Sprint Plan

**Duration:** January 15 - April 2, 2025

**Goal:** 5 Customers Using by March 31

---

## Initiative Overview

### Objectives

- Rebuild inventory builder with completely new UI
- Achieve feature parity by March 16, 2025
- **5 customers using by March 31, 2025**

### Approach

Hybrid methodology: Build minimal viable journey first (Weeks 1-3), then complete core functionality with depth (Weeks 4-9). Customer rollout starts Step 10 (March 19) with concurrent development.

**Key principle:** Break work into small, parallel-trackable epics. Some may take 1-1.5 weeks, allowing flexible team allocation.

### Timeline

- **Start:** January 15, 2025
- **Customer Rollout:** March 19, 2025
- **Deadline:** March 31, 2025

---

## Phase 1: Foundation

**Duration:** Weeks 1-3 | Minimal Viable Journey

**Goal:** Working CSV import + Diagram recognition foundation

### Step 1: Basic CSV Import

#### Problem Statement

Users need a simple way to import inventory data from CSV files. Current system lacks a modern, guided import experience. This epic delivers the foundation wizard framework that will be reused for all import types.

#### Key Functionality (Requirements)

- 2-step wizard stepper component (based on Figma designs)
- Navigation between steps
- File upload UI (drag-drop, validation)
- CSV validation
- Meaningful error messages
- CSV extracted results shown in "Review and Import" step
- Does not need to be a compliant table for the moment

#### Success Criteria

Users can upload CSV files, see validation errors, and navigate through wizard steps

#### Sprint Review Script

**Demo Flow:**
1. Show the new import wizard entry point
2. Demonstrate drag-and-drop file upload (use a sample CSV)
3. Show file validation (try uploading invalid file to show error messages)
4. Navigate through the 2-step wizard (highlight the stepper component)
5. Show CSV preview in the "Review" step with extracted data

**Key Talking Points:**
- This wizard framework will be reused for all import types (CSV, images, Excel)
- Modern UI follows LeanIX design system
- Clear validation prevents bad data early
- Foundation complete for Step 2 mapping functionality

#### Limitations/Out of Scope

- No actual import execution (Step 2)
- No column mapping (Step 2)
- No support for Excel files (Step 12+)
- No advanced CSV formats (multi-line cells, complex delimiters)

#### Visuals/Mockups & Relevant URLs

**Key UI Components (from Figma):**
- **File upload modal:** Drag-drop zone with file type indicators (.csv, .png, .jpg)
- **Stepper component:** 3-step wizard (File analysis → Map Content → Review & Import)
- **Validation messaging:** Clear error display with file size limits
- **Loading state:** "Analyzing" screen with progress indicator

**Links:**
- [Productboard: View Epic](https://leanix.productboard.com/all-notes/notes/52999760)
- [Figma: View Design](https://www.figma.com/design/g6sf9m99hum60c0Z3XaC6L/Unified-import-exploration?node-id=4219-23631&p=f&t=JE0CmcfBuHGyuWW0-0)

---

### Step 2: Mapping & Import

#### Problem Statement

Users need to map CSV columns to inventory fields and execute imports. This completes the end-to-end CSV import journey, enabling the first demo to stakeholders.

#### Key Functionality (Requirements)

- Fixed mapping (Applications only)
- Column-to-field assignment with AI suggestions
- Review screen & Import execution

#### Success Criteria

**🎯 End-to-end CSV → Applications working**

#### Sprint Review Script

**Demo Flow:**
1. Start with a sample CSV containing 10-15 Application records
2. Show the complete wizard flow from upload to mapping
3. Highlight AI-powered column suggestions ("Application Name" → "Name")
4. Show manual override (change a suggestion to demonstrate flexibility)
5. Execute import and show success notification
6. Navigate to inventory and show the newly imported Applications

**Key Talking Points:**
- **First milestone:** Complete end-to-end working flow ready for stakeholder demo
- AI reduces manual mapping effort by 70%+ (show time savings)
- Foundation established for adding more fact sheet types (Step 6)
- Ready to start customer feedback collection

**Expected Questions & Answers:**
- Q: "Can we import other types?" → A: "Step 6, focusing on Applications first"
- Q: "What about relationships?" → A: "Step 7 for CSV, Step 5 for diagrams"
- Q: "How accurate is AI mapping?" → A: "Show live accuracy metrics"

#### Limitations/Out of Scope

- Only Applications fact sheet type (other types in Step 6)
- No relationship mapping (CSV relationships in Step 7)
- No duplicate detection or update mode (Step 8 validation)
- No advanced validation rules (Step 8)
- No import history/audit log (Step 9+)
- No template/configuration saving (Step 11)
- No bulk remap across multiple files
- No Excel file support (Step 12+ post-Q1)

#### Dependencies

- Step 1 wizard framework complete
- AI service for mapping suggestions (evaluation by Jan 17)
- Backend import API endpoints ready

---

### Step 3: Image Detection

#### Problem Statement

Users want to import inventory from architecture diagrams. This epic establishes the foundation for diagram-based imports by extracting objects from images using AI/vision services.

#### Key Functionality (Requirements)

- Image file support (.png, .jpg)
- AI/Vision service integration for object extraction
- Extract objects with labels, colors, positions
- Display detected objects in list view

#### Success Criteria

**🎯 Diagram upload with object extraction working**

#### Sprint Review Script

**Demo Flow:**
1. Upload the TechSolutions architecture diagram (.png)
2. Show the "Analyzing..." loading state with progress indicator
3. Display the diagram preview with detected object highlights
4. Show the list of extracted objects with their metadata (labels, colors, positions)
5. Zoom in on specific detected boxes to show accuracy
6. Try a second diagram to show consistency

**Key Talking Points:**
- **Key differentiator:** Import from visual diagrams, not just structured data
- Vision AI extracts 85%+ of objects accurately
- Foundation for Step 4 (classification) and Step 5 (relationships)
- Works with common architecture diagram formats (.png, .jpg)

**Expected Questions & Answers:**
- Q: "What about Visio files?" → A: "Post-Q1, focusing on images first"
- Q: "Can we edit detected objects?" → A: "Step 4 adds manual editing"
- Q: "What about connections?" → A: "Step 5 detects relationships"

#### Limitations/Out of Scope

- No object classification/type assignment (Step 4)
- No relationship/connection detection (Step 5)
- No manual editing of detected objects (Step 4)
- No batch processing of multiple diagrams
- No support for PDF/Visio files (post-Q1)
- No support for complex diagram formats (multi-page, embedded images)
- No re-training or learning from corrections (future enhancement)
- No diagram validation or quality scoring

#### Dependencies

- AI/Vision service provider selected by Jan 17
- Service API keys and access provisioned
- Step 1 wizard framework (reuse for image upload)
- Backend storage for images and metadata

---

## Phase 2: Diagram Recognition

**Duration:** Weeks 4-5 | Complete Diagram Workflow

**Goal:** Full diagram-to-inventory workflow (AI for mapping suggestions, not re-extraction)

### Step 4: Object Classification

#### Problem Statement

Detected objects need to be classified into fact sheet types (Application, Server, etc.) to be imported. AI suggestions reduce manual effort. Manual editing provides control and accuracy. This bridges diagram extraction to actual inventory data.

#### Key Functionality (Requirements)

- AI classification of objects to fact sheet types (based on labels/colors/context)
- Enhanced list/table view with suggested types and confidence scores
- Manual type correction via dropdown (all available fact sheet types)
- Add new objects manually (not detected by AI)
- Delete incorrect/unwanted objects
- Bulk classification: "Apply to all similar" based on pattern matching
- Visual feedback on classification status (classified vs. pending)

#### Success Criteria

- All detected objects can be classified and edited, ready for relationship mapping
- AI classification achieves >70% accuracy on test diagrams

#### Limitations/Out of Scope

- No relationship detection (Step 5)
- No field-level mapping (reuses Step 2 mapping step)
- No learning from user corrections (future enhancement)
- Limited to fact sheet types only (no sub-types)

#### Dependencies

- Step 3 object detection complete
- AI/ML model for classification (may be same service as Step 3)
- Fact sheet type metadata API

---

### Step 5: Relationships (Diagram)

#### Problem Statement

Architecture diagrams contain connections/arrows showing relationships. Detecting and classifying these completes the diagram import workflow. This is a key differentiator - importing both entities AND relationships from visual diagrams.

#### Key Functionality (Requirements)

- Detect connections/arrows between classified objects
- AI suggestion of relationship types based on context and labels
- Manual relationship type editing (dropdown with available types)
- Add relationships manually if not detected
- Delete incorrect relationships
- Visual representation of relationships on diagram preview
- Flow into mapping step (reuse Step 2 mapping UI)
- Bulk remap functionality for relationship attributes

#### Success Criteria

- **🎯 Complete diagram → inventory workflow**
- Users can import objects AND relationships from diagrams end-to-end

#### Limitations/Out of Scope

- CSV relationship import (Step 7)
- Complex relationship attributes/metadata
- Bidirectional relationship handling
- Relationship validation rules (Step 8)

#### Dependencies

- Step 4 object classification complete
- Relationship types metadata API
- Step 2 mapping framework (reuse)

**Note:** AI is applied to mapping suggestions (which type, which relationship), not to re-extracting objects from the image. Once extracted, the data is deterministic.

---

## Phase 3: Core Completion

**Duration:** Weeks 6-9 | Feature Parity & Polish

**Goal:** Complete all fact sheet types, relationships, validation, and performance optimization

**✅ Core complete by March 18, 2025**

### Step 6: All Fact Sheet Types

#### Problem Statement

Currently limited to Applications. Users need to import all fact sheet types (Servers, Databases, Business Capabilities, etc.). This makes the tool viable for diverse inventory scenarios and achieves feature parity with old system.

#### Key Functionality (Requirements)

- Dynamic fact sheet type selection in wizard
- Fetch available types from backend metadata API
- Dynamic field mapping based on selected type
- Support for custom fields per type
- Type-specific validation rules
- Mixed type import from single CSV (advanced mode)

#### Success Criteria

Users can import any fact sheet type from CSV with proper field mapping

#### Limitations/Out of Scope

- No custom type creation (use existing types only)
- No complex field types (multi-select, nested objects) - treat as strings
- No cross-type dependencies within single import

#### Dependencies

- Weeks 1-2 CSV import framework
- Backend metadata API for all fact sheet types
- Type-specific validation rules documented

---

### Step 7: Relationships (CSV)

#### Problem Statement

Users need to import relationships from CSV files (not just diagrams). Common scenario: separate CSVs for entities and relationships. This achieves full relationship import capability across both import methods.

#### Key Functionality (Requirements)

- Import mode selection: Entities only, Relationships only, or Both
- CSV format for relationships (from_id, to_id, type, metadata)
- Relationship type selection and mapping
- Reference resolution (match IDs to existing entities)
- Validation: ensure both ends of relationship exist
- Bulk relationship import with progress tracking
- Error handling for missing references

#### Success Criteria

Users can import relationships from CSV, with proper validation and error handling

#### Limitations/Out of Scope

- No automatic entity creation from relationship references
- No many-to-many relationship expansion
- No relationship deduplication (Step 8)

#### Dependencies

- Step 5 relationship concepts and data model
- Backend relationship import API
- Entity lookup/search API for reference resolution

---

### Step 8: Validation & Data Quality

#### Problem Statement

Before customer rollout, need robust validation to prevent bad data. Includes duplicate detection, required field enforcement, data type validation, and business rule checks. Critical for customer success.

#### Key Functionality (Requirements)

- Duplicate detection (exact and fuzzy matching)
- Update vs. Create mode selection
- Required field validation with clear error messages
- Data type validation (dates, numbers, emails, URLs)
- Business rule validation (type-specific rules)
- Validation summary with error/warning counts
- Partial import option: proceed with valid rows, skip invalid

#### Success Criteria

- Validation prevents bad data imports and provides clear feedback
- **⚠️ Identify & warm up 5 customers for rollout**

#### Limitations/Out of Scope

- No custom validation rule creation
- No ML-based duplicate detection (simple string matching)
- No data transformation/cleaning features

#### Dependencies

- All import types complete (Weeks 1-7)
- Validation rules specification document
- Backend validation service

**⚠️ Customer Preparation (Non-Dev Task):** By end of this step, CSM/Product must identify 5 customers for rollout starting Step 10

---

### Step 9: Performance & Polish

#### Problem Statement

Final step before customer rollout. Focus on performance optimization, error handling, loading states, and polish. Ensures smooth customer experience from day one. This is core completion milestone.

#### Key Functionality (Requirements)

- Large file handling (chunked processing, streaming)
- Progress indicators for all async operations
- Background import processing with notifications
- Performance testing and optimization (>1000 rows)
- Error recovery and retry mechanisms
- Loading states and skeleton screens
- Browser performance testing (memory, CPU)
- Final UX polish pass

#### Success Criteria

- **✅ Core functionality complete - Ready for customer rollout**
- Can import 5000+ rows in <5 min, smooth UI with no blocking operations

#### Limitations/Out of Scope

- Advanced features (templates, scheduling) in Weeks 10-11
- Excel support (Step 12+)
- Import history/audit log (future)

#### Dependencies

- All features from Weeks 1-8 complete
- Performance benchmarking tools setup
- Test data sets (small, medium, large)

---

## Phase 4: Customer Rollout

**Duration:** Weeks 10-11 | Launch & Scale

**🎯 CRITICAL GOAL: 5 customers actively using by March 31, 2025**

### Step 10: Reliability + ROLLOUT

#### Problem Statement

First customer rollout step. Focus on reliability, monitoring, error tracking, and support readiness. Concurrent development of nice-to-have features while onboarding first 2-3 customers.

#### Key Functionality (Requirements)

- **Reliability:** Error tracking, logging, monitoring dashboards
- **Support:** Customer onboarding materials, video tutorials
- **Rollout:** Onboard first 2-3 customers with hands-on support
- Import history/audit log (who imported what when)
- Rollback capability for failed imports
- Real-time support channel (Slack/Teams integration)
- Feedback collection mechanism

#### Success Criteria

- **🚀 INITIAL ROLLOUT - First 2-3 customers onboarded**
- Customers successfully import real data with support, no critical bugs

#### Limitations/Out of Scope

- Full self-service onboarding (provide hands-on support this step)
- Advanced power features (Step 11)
- Automated customer health monitoring (future)

#### Dependencies

- Step 9 core complete and stable
- 5 customers identified and prepped (from Step 8)
- Support team trained and ready
- Monitoring/logging infrastructure ready

**⚠️ Critical Actions:**
- Schedule kickoff calls with first 2-3 customers
- Daily stand-ups to track rollout progress
- On-call rotation for immediate issue response

---

### Step 11: Power Features + ROLLOUT

#### Problem Statement

Final push to reach 5 customers by March 31. Add power features that improve efficiency for advanced users. Incorporate feedback from Step 10 customers. This is the deadline step.

#### Key Functionality (Requirements)

- **Rollout:** Onboard remaining 2-3 customers (reach 5 total)
- **Templates:** Save and reuse mapping configurations
- **Scheduling:** Schedule recurring imports (optional, if time)
- Bulk operations: Multi-file import queue
- Advanced filters in review step
- Export mapping configuration for sharing
- Incorporate feedback from Step 10 customers

#### Success Criteria

- **🎯 DEADLINE: 5 customers actively using by March 31**
- All 5 customers have completed at least one successful import

#### Limitations/Out of Scope

- Excel support (Step 12 - Post-Q1)
- Advanced scheduling (basic only if time permits)
- API for programmatic imports (future)

#### Dependencies

- Step 10 rollout stable and successful
- Feedback from first customers collected
- Remaining 2-3 customers ready to onboard

**🎯 Deadline: March 31, 2025**
- 5 customers must be actively using the new inventory builder
- Daily check-ins with customers to ensure success

---

## Timeline Overview

| Step | Dates | Focus | Milestone |
|------|-------|-------|-----------|
| 1 | Jan 15-21 | CSV upload | Foundation |
| 2 | Jan 22-28 | Mapping & import | 🎯 First demo |
| 3 | Jan 29-Feb 4 | Image detection | AI integration |
| 4 | Feb 5-11 | Object classification | Diagram editing |
| 5 | Feb 12-18 | Relationships | 🎯 Diagram complete |
| 6 | Feb 19-25 | All fact sheet types | Dynamic types |
| 7 | Feb 26-Mar 4 | Relationships (CSV) | Full relationships |
| 8 | Mar 5-11 | Validation | ⚠️ ID 5 customers |
| 9 | Mar 12-18 | Performance | ✅ Core complete |
| **10** | **Mar 19-25** | **Reliability + ROLLOUT** | **🚀 2-3 customers** |
| **11** | **Mar 26-Apr 1** | **Power features + ROLLOUT** | **🎯 5 customers** |
| 12 | Apr 2-8 | Excel support | Post-Q1 |
| 13 | Apr 9-15 | Templates & polish | Post-Q1 |

**Critical:** Core complete by March 18 | Customer rollout starts March 19 | 5 customers by March 31

---

## Critical Success Points

### ✅ Step 2 (Jan 28)
Working demo for stakeholders

### ✅ Step 5 (Feb 18)
Diagram import workflow complete

### ⚠️ Step 8 (Mar 11)
Core validation complete + **Identify & warm up 5 customers**

### ✅ Step 9 (Mar 18)
**Core functionality complete - Ready for customer rollout**

### 🚀 Step 10 (Mar 19)
**INITIAL ROLLOUT - First 2-3 customers onboarded**

### 🎯 Step 11 (Mar 31)
**DEADLINE: 5 customers actively using the new inventory builder**

---

## Next Steps & Risk Mitigation

### Immediate Actions (Step 1)

1. **Review Figma Designs:** Confirm 3-step wizard structure with team (Ania's designs)
2. **AI/Vision Service Selection:** Evaluate and select provider by Jan 17
3. **Team Allocation:** Assign frontend, backend, and AI integration resources
4. **Epic Breakdown:** Create small, parallel-trackable epics (Step 6+ can split)

### Critical: Customer Preparation (Step 8)

By **March 11**, identify and prepare 5 customers:
- Select customers who frequently use inventory import
- Brief them on timeline and expectations
- Prepare onboarding materials
- Schedule kickoff meetings for Step 10 (March 19)

### Success Criteria

✅ Working demo by **Jan 28**
✅ Diagram import by **Feb 18**
✅ Core complete by **Mar 18**
✅ Customer rollout **Mar 19**
🎯 **5 customers using by Mar 31**

---

## Feature Checklist

### Required Features

1. **CSV File Import** - High Priority (Step 1)
   - Upload and parse CSV files with drag-and-drop support

2. **Multi-step Wizard Component** - High Priority (Step 1)
   - Reusable wizard stepper with navigation and validation

3. **Column Mapping UI** - High Priority (Step 2)
   - Map CSV columns to inventory fields with AI suggestions

4. **Diagram Image Upload** - Medium Priority (Step 3)
   - Support for PNG/JPG diagram uploads

5. **AI Object Detection** - High Priority (Step 3)
   - Detect objects in architecture diagrams using vision API

6. **Object Classification** - High Priority (Step 4)
   - Classify detected objects into fact sheet types (Application, Server, etc.)

7. **Relationship Detection (Diagrams)** - Medium Priority (Step 5)
   - Detect and classify arrows/connections in diagrams

8. **All Fact Sheet Type Support** - High Priority (Step 6)
   - Support import for all fact sheet types (not just Applications)

9. **Data Validation Engine** - High Priority (Step 8)
   - Duplicate detection, required fields, data type validation

10. **Import Error Recovery** - Medium Priority (Step 9)
    - Resume failed imports and handle large files

---

## Resources

### Design & Documentation Links

- **Figma Designs:** [Unified import exploration](https://www.figma.com/design/g6sf9m99hum60c0Z3XaC6L/Unified-import-exploration?node-id=4219-23631&p=f&t=JE0CmcfBuHGyuWW0-0)
- **Productboard - Step 1:** [View Epic](https://leanix.productboard.com/all-notes/notes/52999760)
- **Productboard - Step 2:** [View Epic](https://leanix.productboard.com/all-notes/notes/53008356)
- **Productboard - Step 3:** [View Epic](https://leanix.productboard.com/all-notes/notes/53013420)

### Key UI Components

1. **File Upload Modal** - Drag-drop zone with file type indicators (.csv, .png, .jpg)
2. **Stepper Component** - 3-step wizard (File analysis → Map Content → Review & Import)
3. **Mapping Interface** - Two-column layout with AI-powered suggestions
4. **Review Table** - Data table with checkboxes, type dropdowns, status badges
5. **Import Overview Dashboard** - Statistics cards and file list with status
6. **Analysis Loading State** - Animated loader with "Analyzing..." message

---

*Document generated January 28, 2025*
*Last updated: January 28, 2025*
