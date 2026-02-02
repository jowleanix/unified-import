# Timeline Consistency Analysis

## Executive Summary

Based on analysis of 35 features from sprint plans, Productboard insights, and customer interviews, the current 11-step timeline has **significant imbalances** that should be addressed.

### Key Issues Identified

1. **Step 2 is overloaded**: 6 features (4 high-priority) including mapping, templates, validation visibility
2. **Step 7 is missing**: No features mapped to "Relationships (CSV)" - appears redundant
3. **Step 8 is severely overloaded**: 9 features including entire review/validation experience
4. **Steps 5, 10, 11 are underutilized**: Only 1 feature each
5. **Customer priorities misaligned**: High-priority governance and review features buried in Step 8

---

## Current Distribution

| Step | Title | Features | High Priority | Issue |
|------|-------|----------|---------------|-------|
| 1 | Basic CSV Import | 4 | 4 | ✅ Balanced |
| 2 | Mapping & Import | 6 | 4 | ⚠️ Overloaded |
| 3 | Image Detection | 5 | 3 | ✅ Acceptable |
| 4 | Object Classification | 3 | 1 | ✅ Balanced |
| 5 | Relationships (Diagram) | 1 | 0 | ⚠️ Underutilized |
| 6 | All Fact Sheet Types | 4 | 2 | ✅ Balanced |
| 7 | Relationships (CSV) | 0 | 0 | 🚨 Empty |
| 8 | Validation & Data Quality | 9 | 4 | 🚨 Severely Overloaded |
| 9 | Performance & Polish | 2 | 1 | ✅ Balanced |
| 10 | Reliability + ROLLOUT | 1 | 1 | ⚠️ Underutilized |
| 11 | Power Features + ROLLOUT | 1 | 0 | ⚠️ Underutilized |

**Total**: 35 features, 20 high-priority (57%)

---

## Critical Findings

### 1. Step 8 is a Bottleneck (9 features)

Step 8 currently includes:
- **Core Validation**: Duplicate detection, required fields, data type validation
- **Governance**: Two-stage approval workflow (large enterprise requirement)
- **Review UX**: Visual differentiation, inline editing, relationship diagrams
- **Review Tools**: Bulk import button, error-only filters, subtype selection
- **Field Control**: Granular update control (preserve vs. update specific fields)

**Problem**: This is actually 3-4 different functional areas crammed into one sprint:
1. Validation Engine (backend logic)
2. Governance/Approval Workflow (enterprise feature)
3. Review Interface (UX layer)
4. Bulk Operations (productivity tools)

### 2. Step 7 is Redundant

"Relationships (CSV)" has zero features mapped. Customer interviews show:
- Relationships are handled regardless of source (diagram or CSV)
- Delimiter configuration (comma vs semicolon) is a mapping concern, not a separate step
- No customer mentioned CSV relationships as distinct from diagram relationships

**Evidence**: VW interview discusses relationships in context of overall import, not as separate CSV workflow.

### 3. Mapping Templates are Critical but Buried

**INT-005** (Save & Reuse Mapping Templates) is:
- HIGH priority from multiple customers (VW, Marianne)
- Mentioned as fundamental need for recurring imports
- Required for org standardization
- Currently one of 6 features in Step 2

**Customer Quote** (VW): *"I would be able to save this mapping... reuse and share the same template across the organization"*

### 4. Governance is Enterprise Blocker

**INT-001** (Staging Area for Import Governance) is:
- HIGH priority for large enterprises (7,000+ users)
- Prevents mass rollout without approval workflow
- Currently buried as 1 of 9 features in Step 8

**Customer Quote** (VW): *"we would have actually made it a two stage approach... everyone would be able to push the stuff in and then they would have needed to committed it to the inbox and we would have then cleared it from that inbox as a central team"*

### 5. Export/Re-Import is Common Pattern

**FR-ib-007** (Export/Enrich/Re-Import Workflow) is:
- HIGH priority from Productboard
- Common pattern: export → enrich in Excel/Copilot → re-import
- Should be foundational, not one of 6 features in Step 2

---

## Recommended Reorganization

### Option A: Restructure into 12 Steps (Minimal Change)

#### Phase 1: Foundation (Weeks 1-3)
- **Step 1: Upload & Configuration** *(unchanged)*
  - CSV import, wizard, prompt templates, system user context

- **Step 2: Basic Column Mapping** *(split from current Step 2)*
  - Column mapping UI
  - Interactive wizard
  - Preview mode

- **Step 2B: Advanced Mapping** *(new - split from Step 2)*
  - Save/reuse mapping templates ⭐ HIGH PRIORITY
  - Data type & validation visibility ⭐ HIGH PRIORITY
  - Export/enrich/re-import workflow ⭐ HIGH PRIORITY

#### Phase 2: Diagram Recognition (Weeks 4-5)
- **Step 3: Image Detection** *(unchanged)*

- **Step 4: Object Classification** *(unchanged)*

- **Step 5: Relationship Detection** *(merged with old Step 7)*
  - Relationship detection (diagrams)
  - Relationship import (CSV) - **merged from Step 7**
  - Delimiter configuration

#### Phase 3: Core Completion (Weeks 6-9)
- **Step 6: All Fact Sheet Types** *(unchanged)*

- **Step 7: Core Validation** *(new - split from Step 8)*
  - Validation engine (duplicates, required fields, data types)
  - Automatic import source tagging

- **Step 8: Review Interface** *(new - split from old Step 8)*
  - Visual import action differentiation ⭐ HIGH PRIORITY
  - Inline editing in review
  - Relationship diagram in review
  - Subtype selection
  - Bulk import all button
  - Error-only filter view

- **Step 9: Import Governance** *(new - split from old Step 8)*
  - Staging area for import governance ⭐ HIGH PRIORITY
  - Granular field-level update control ⭐ HIGH PRIORITY

#### Phase 4: Customer Rollout (Weeks 10-11)
- **Step 10: Performance & Polish** *(merged old 9+10)*
  - Error recovery
  - Recently imported items filter

- **Step 11: Power Features + ROLLOUT** *(unchanged)*

---

### Option B: Refactor by Customer Journey (Moderate Change)

Reorganize to match actual customer workflow:

#### Phase 1: Prepare (Weeks 1-2)
1. **Upload & Configure**
2. **Map with Templates** (mapping + templates + validation visibility)

#### Phase 2: Detect & Classify (Weeks 3-5)
3. **Diagram Detection** (image upload + object detection + format training)
4. **Object Classification** (classification + soft delete + re-prompt)
5. **Relationships** (both diagram and CSV)

#### Phase 3: Review & Validate (Weeks 6-8)
6. **Core Validation** (validation engine)
7. **Review Interface** (visual diff, inline editing, filters, bulk operations)
8. **Update Control** (granular field control, subtype selection)

#### Phase 4: Govern & Import (Week 9)
9. **Import Governance** (staging/approval workflow + tagging)

#### Phase 5: Scale & Optimize (Weeks 10-11)
10. **All Fact Sheet Types** (multi-type support + join attributes + export views)
11. **Power Features** (saved views, scheduled exports, recently imported filter)

---

## Specific Recommendations

### 🚨 Critical Changes (Must Do)

1. **Split Step 8 into 3 steps**:
   - Step 7: Core Validation (technical/backend)
   - Step 8: Review Interface (UX/frontend)
   - Step 9: Import Governance (enterprise feature)

2. **Merge Step 7 into Step 5**:
   - Rename Step 5 to "Relationship Detection (All Sources)"
   - Include both diagram and CSV relationship handling

3. **Elevate Mapping Templates**:
   - Split Step 2 to give templates dedicated focus
   - Critical for customer adoption and recurring imports

### ⚠️ Important Changes (Should Do)

4. **Move governance earlier** (or make it optional/parallel):
   - Large enterprises won't adopt without approval workflow
   - Consider making it a toggle: "Enable Staging Mode" in Step 1

5. **Group review features together**:
   - Inline editing, visual diff, filters, bulk operations are one cohesive UX
   - Should be designed and implemented as a unit

6. **Consider parallel tracks**:
   - CSV track: Steps 1-2 → Skip 3-5 → Step 6-11
   - Diagram track: Steps 1-5 → Step 6-11
   - This matches actual customer usage patterns

### ✅ Optional Improvements (Nice to Have)

7. **Add "Quick Wins" step**:
   - System user context (INT-002)
   - Automatic tagging (INT-008)
   - Recently imported filter (INT-007)
   - These are small, high-impact features that could be done early

8. **Rename steps for clarity**:
   - "Validation & Data Quality" → "Core Validation Engine"
   - "Performance & Polish" → "Scale & Reliability"
   - Use customer-facing language, not technical jargon

---

## Feature Priority Alignment

### HIGH Priority Features (20 total)

Currently distributed:
- **Step 1**: 4 high-priority ✅ Good
- **Step 2**: 4 high-priority ⚠️ Too many with 6 total features
- **Step 3**: 3 high-priority ✅ Acceptable
- **Step 6**: 2 high-priority ✅ Good
- **Step 8**: 4 high-priority 🚨 Too many with 9 total features
- **Step 9**: 1 high-priority ✅ Good
- **Step 10**: 1 high-priority ✅ Good
- **Steps 4, 5, 11**: 0 high-priority ⚠️ Opportunity to rebalance

**Recommendation**: Distribute high-priority features more evenly across steps to avoid bottlenecks in Steps 2 and 8.

---

## Risk Analysis

### Timeline Risks

1. **Step 8 as currently scoped will slip**:
   - 9 features in one step is unrealistic
   - 4 high-priority features = high complexity
   - Review UX typically requires multiple iterations

2. **Missing governance blocks enterprise adoption**:
   - VW (7,000 users) explicitly said they need staging/approval
   - Without INT-001, large customers won't enable for end users

3. **Mapping templates are foundational**:
   - If templates arrive late in Step 2, customers create ad-hoc processes
   - Need templates early to standardize across organization

### Sequencing Risks

1. **Step 7 redundancy creates confusion**:
   - Empty step suggests incomplete planning
   - Relationships should be handled uniformly regardless of source

2. **Review features split from validation**:
   - Review interface (Step 8) needs validation engine working
   - Can't test review UX without validation logic
   - Suggests Step 7 (validation) and Step 8 (review) are sequential dependencies

---

## Customer Journey Validation

Based on interview analysis:

### VW (Large Enterprise) Journey
1. ✅ Upload with system user context
2. ✅ Map with templates (recurring imports)
3. ❌ **BLOCKER**: Need staging area for central team approval
4. ✅ Review with visual diff (see what's new vs. updated)
5. ✅ Granular field control (update lifecycle, preserve descriptions)
6. ✅ Filter to recently imported items to verify

**Insight**: Governance is a hard requirement, not a nice-to-have. Step 8 split is mandatory.

### Marianne (Business User) Journey
1. ✅ Upload CSV
2. ✅ Map columns with search (large attribute lists)
3. ✅ Review with error-only filter (500 rows)
4. ✅ Bulk "Import All" button
5. ✅ Assign subtypes in review (avoid post-import work)
6. ✅ Done!

**Insight**: Review UX features (filters, bulk operations, inline editing) are one cohesive experience. Step 8 split makes sense.

### NTT (Integration User) Journey
1. ✅ Upload CSV
2. ✅ Map columns
3. ⚠️ Want AI suggestions WITHOUT prompts upfront (auto-detect)
4. ✅ Review and adjust
5. ✅ Auto-tag imports by source
6. ✅ Filter to recently imported items

**Insight**: AI features should be seamless, not require prompt writing. FR-ib-005 (prompt templates) addresses this.

---

## Recommended Action Plan

### Immediate (This Week)
1. **Split Step 8 into 3 steps** (Critical Path Item)
2. **Merge Step 7 into Step 5** (Remove Empty Step)
3. **Update phase boundaries** to reflect new structure

### Short Term (Next Sprint)
4. **Re-sequence features** based on dependencies
5. **Validate with stakeholders** (especially enterprise customers)
6. **Update Figma designs** to match new step structure

### Medium Term (Next Month)
7. **Consider parallel tracks** (CSV vs. Diagram) for flexibility
8. **Add optional governance toggle** for different customer sizes
9. **Create "Quick Wins" milestone** with high-impact, low-effort features

---

## Conclusion

The current timeline has **3 critical issues**:

1. ✅ **Step 2 Overload**: 6 features, 4 high-priority → **Split into Steps 2 and 2B**
2. ✅ **Step 7 Empty**: 0 features → **Merge into Step 5**
3. 🚨 **Step 8 Overload**: 9 features, 4 high-priority → **Split into Steps 7, 8, 9**

**Recommended Structure** (Option A - Minimal Change):
- Phase 1: Steps 1, 2, 2B (was 1-2)
- Phase 2: Steps 3, 4, 5 (was 3-5, merged 7)
- Phase 3: Steps 6, 7, 8, 9 (was 6-9, split 8 into 3)
- Phase 4: Steps 10-11 (merged old 9-10)

This results in **12 steps** with better distribution:
- No step has more than 6 features
- High-priority features spread more evenly
- Customer journey is clearer
- Enterprise requirements (governance) get dedicated focus

**Next Steps**:
1. Review this analysis with product team
2. Decide between Option A (12 steps) or Option B (refactor by customer journey)
3. Update timeline.html with new structure
4. Re-baseline Figma designs and Productboard links
5. Communicate changes to stakeholders
