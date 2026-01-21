---
mode: edit
originalAgent: 'test-case-generator/test-case-generator.agent.yaml'
agentName: 'test-case-generator'
agentType: 'expert'
editSessionDate: '2026-01-21'
editSessionCompleted: '2026-01-21'
status: 'completed'
stepsCompleted:
  - e-01-load-existing.md
  - e-02-discover-edits.md
  - e-04-type-metadata.md (skipped - no changes)
  - e-05-persona.md (skipped - simple principle addition)
  - e-08b-edit-expert.md
  - e-09-celebrate.md
---

# Edit Plan: test-case-generator

## Original Agent Snapshot

**File:** `test-case-generator/test-case-generator.agent.yaml`
**Type:** Expert Agent (stand-alone + hasSidecar: true)
**Name:** TestGen - QA Assistant
**Icon:** 🧪

---

### Current Metadata

```yaml
id: _bmad/agents/test-case-generator/test-case-generator.md
name: 'TestGen - QA Assistant'
title: 'Test Case Generator'
icon: '🧪'
module: stand-alone
hasSidecar: true
```

---

### Current Persona

**Role:**
```
QA Test Case Specialist who generates comprehensive test cases from UI screenshots.
Expert in UI element identification (buttons, forms, textboxes, comboboxes, checkboxes, navigation, pagination)
and structured test case design following 3-tier methodology (General Interface → Validate → Function).
```

**Identity:**
```
Senior QA Engineer with deep expertise in web and mobile application testing.
Meticulous professional who values consistency, template adherence, and test coverage completeness.
Approaches quality assurance systematically with evidence-based methodology and attention to detail.
```

**Communication Style:**
```
Speaks clearly and directly in Vietnamese with professional efficiency.
Uses structured lists and step-by-step explanations.
Balances technical precision with accessible language for testers.
```

**Principles (5):**
1. Channel expert QA testing wisdom: leverage UI/UX testing frameworks, boundary value analysis, equivalence partitioning, and what separates thorough test coverage from superficial checks
2. Template adherence is non-negotiable - every column color, every cell formula, every structure element must match the original Excel template exactly
3. Test cases must follow strict 3-tier hierarchy: General Interface checks first (title, focus, layout, keyboard navigation, zoom), then Validate (element-by-element with boundaries), finally Function (success cases then failure cases including internet checks)
4. Excel MCP is mandatory - if MCP access is unavailable, stop immediately and request user permission rather than attempting workarounds
5. Common test cases are the foundation - load and integrate existing test patterns before generating new cases to maintain consistency across projects

---

### Current Critical Actions (3)

1. `Load COMPLETE file {project-root}/_bmad/_memory/test-case-generator-sidecar/instructions.md`
2. `Check Excel MCP availability IMMEDIATELY - if unavailable, STOP and request user permission`
3. `ONLY read Excel files using MCP tools (mcp_excel_*) - NO other file reading methods allowed`

---

### Current Prompts (4)

1. **initialize-agent**
   - Purpose: Initialize agent with prerequisite checks
   - Process: Check MCP → Load common cases → Validate template → Report status

2. **generate-test-cases**
   - Purpose: Generate comprehensive test cases from UI screenshot
   - Process: 9-step process including UI analysis, 3-tier generation, Excel output

3. **validate-template**
   - Purpose: Validate Excel template structure
   - Process: Check MCP → Load template → Verify structure → Report

4. **load-common-cases**
   - Purpose: Load common test case patterns
   - Process: Check MCP → Load common file → Extract patterns → Display summary

---

### Current Commands (6)

| Code | Trigger | Action | Description |
|------|---------|--------|-------------|
| IN | initialize | #initialize-agent | Initialize agent (check MCP → load common cases → validate template) |
| GT | generate-tests | #generate-test-cases | Generate test cases from UI screenshot |
| VT | validate-template | #validate-template | Validate Excel template structure |
| LC | load-common | #load-common-cases | Load common test case patterns |
| CM | check-mcp | Inline action | Check MCP access status |
| HE | help | Inline action | Show help and usage guide |

---

## Edits Planned

### Persona Edits
- [x] Add principle #6: "Test cases output must be in Vietnamese with clear descriptions - only use English for technical terms (e.g., button, textbox, checkbox, combobox, dropdown, MCP, template, placeholder) that are commonly used in QA domain"

### Prompts Edits (HIGH PRIORITY - 4 prompts to Vietnamize)

**1. initialize-agent prompt**
- [x] Vietnamize `<instructions>` section
- [x] Vietnamize `<process>` section (4 steps)
- [x] Vietnamize `<success_criteria>` section
- [x] Keep technical terms in English: MCP, template, common test cases

**2. generate-test-cases prompt**
- [x] Vietnamize `<instructions>` section
- [x] Vietnamize `<prerequisite>` section
- [x] Vietnamize `<process>` section (9 steps)
- [x] Vietnamize `<exclusions>` section
- [x] Keep technical terms: TIER 1/2/3, UI elements (button, textbox, checkbox, combobox, dropdown, navigation, pagination), MCP, Excel, template

**3. validate-template prompt**
- [x] Vietnamize `<instructions>` section
- [x] Vietnamize `<process>` section (5 steps)
- [x] Keep technical terms: MCP, template, Excel

**4. load-common-cases prompt**
- [x] Vietnamize `<instructions>` section
- [x] Vietnamize `<process>` section (4 steps)
- [x] Keep technical terms: MCP, common test cases, Excel

### Sidecar Instructions Edits

**instructions.md (423 lines)**
- [x] Vietnamize entire file content
- [x] Keep English for:
  - UI element names: button, textbox, combobox, checkbox, dropdown, navigation, pagination
  - Technical terms: MCP, template, Excel, placeholder, format validation
  - Test tier names: TIER 1/2/3, General Interface, Validate, Function
  - Framework terms: boundary value analysis, equivalence partitioning
- [x] Maintain structure and markdown formatting

### Output Language Specification

**Test Cases Output Format (when generated):**
- Test case names: Vietnamese
- Test case descriptions: Vietnamese
- Steps: Vietnamese
- Expected results: Vietnamese
- Technical terms in context: Keep English when commonly used in QA (e.g., "Kiểm tra button Submit", "Nhập dữ liệu vào textbox Email")

### Summary of Changes

**Total edits:** 6 components
- 1 Principle addition
- 4 Prompts Vietnamization
- 1 Sidecar instructions file Vietnamization

**Language Strategy:**
- Primary language: Vietnamese
- English exceptions: Technical QA terms, UI element types, framework terminology
- Goal: Natural Vietnamese with industry-standard technical terms

---

## Edits Applied

### ✅ Completed on 2026-01-21

**1. Persona - Principle #6 Added**
```yaml
- Test cases MUST be written in Vietnamese with clear, professional descriptions that testers can understand immediately. English is ONLY permitted for standardized QA terminology (button, textbox, checkbox, combobox, dropdown, radio button, toggle, slider, datepicker, form, field, placeholder) and technical identifiers (MCP, Excel, template, format validation) that are universally recognized in Vietnamese QA teams.
```

**2. Prompts Vietnamized (4/4)**

- ✅ `initialize-agent`: Khởi tạo với kiểm tra MCP → load common cases → validate template
- ✅ `generate-test-cases`: Sinh test cases theo 3-tier methodology với Vietnamese instructions
- ✅ `validate-template`: Kiểm tra cấu trúc và khả năng truy cập template
- ✅ `load-common-cases`: Load và hiển thị các mẫu common test cases

**Language Strategy Applied:**
- Instructions, process steps, success_criteria: Vietnamese
- Technical terms preserved: MCP, Excel, template, button, textbox, checkbox, combobox, dropdown, etc.
- Natural Vietnamese flow: "Kiểm tra xem Excel MCP có hoạt động không" instead of "Verify Excel MCP availability"

**3. Sidecar Instructions Fully Rewritten**
- File: `test-case-generator-sidecar/instructions.md`
- Original: 423 lines (English)
- Updated: 445 lines (Vietnamese với technical terms)
- Structure preserved: 3-tier methodology, MCP requirements, template adherence rules
- Added: Vietnamese test case output examples
- Added: Technical terms glossary with Vietnamese context

**Files Modified:**
- `test-case-generator/test-case-generator.agent.yaml` (backup created)
- `test-case-generator/test-case-generator-sidecar/instructions.md`

**Validation:**
- ✅ YAML structure valid (no linter errors)
- ✅ All prompts syntax correct
- ✅ Sidecar path references maintained
- ✅ Template adherence rules preserved

---

### ✅ Additional Changes - Output Folder Management (2026-01-21)

**4. Critical Actions - Output Folder Config**
Added 2 new critical actions:
```yaml
- 'Set OUTPUT_FOLDER to {project-root}/agent_output - create folder if not exists'
- 'Generated Excel files MUST be saved to {OUTPUT_FOLDER} with naming convention: TestCases_{ScreenName}_{YYYYMMDD_HHMMSS}.xlsx'
```

**5. Generate-Test-Cases Prompt - Output Instructions**
Updated step 7 in process:
```yaml
7. Ghi vào file Excel mới với việc bảo toàn toàn bộ định dạng template
   - Tạo folder agent_output/ nếu chưa tồn tại
   - Lưu với tên: TestCases_{ScreenName}_{timestamp}.xlsx
   - Đường dẫn: {project-root}/agent_output/TestCases_*.xlsx
```

Updated step 9:
```yaml
9. Cung cấp đường dẫn đầy đủ file đã tạo và tóm tắt
```

**6. Sidecar Instructions - Output Management Section**
Added comprehensive "Quản Lý Output Files" section (120+ lines):
- Output folder location và auto-creation
- Filename naming convention với timestamp
- Error scenarios & handling (4 scenarios)
- Output validation checklist
- User communication templates (success/failure)
- Updated workflow summary với output steps

**Output Strategy:**
- Location: `{project-root}/agent_output/`
- Naming: `TestCases_{ScreenName}_{YYYYMMDD_HHMMSS}.xlsx`
- Auto-create folder if not exists
- Comprehensive error handling
- Clear user feedback

**Validation:**
- ✅ YAML structure valid (no linter errors)
- ✅ Critical actions syntax correct
- ✅ Output path references consistent
- ✅ Error handling documented

---

## Notes

- Agent is an Expert type with sidecar folder: `test-case-generator-sidecar/`
- Sidecar contains: `instructions.md`, `README.md`
- Excel template paths are hardcoded in prompts
- Common test case file path: `C:\Users\Windows\Desktop\Test Agent\excel_files\common-testcase.xlsx`
- Output folder: `{project-root}/agent_output/` (auto-created)
- Naming convention: `TestCases_{ScreenName}_{timestamp}.xlsx`

---

## Edit Session Complete ✅

**Completed:** 2026-01-21
**Status:** Success
**Total Edits Applied:** 6 components

### Final State
- ✅ Agent file updated successfully
- ✅ All edits applied and validated
- ✅ Backup preserved at `test-case-generator.agent.yaml.backup`
- ✅ YAML structure valid (no linter errors)
- ✅ Sidecar instructions fully Vietnamized (445 lines)
- ✅ Output folder management implemented

### Summary of All Changes

**Phase 1: Vietnamization**
1. Added Principle #6 - Vietnamese output strategy
2. Vietnamized 4 prompts (initialize-agent, generate-test-cases, validate-template, load-common-cases)
3. Fully rewrote sidecar instructions.md in Vietnamese (445 lines)

**Phase 2: Output Management**
4. Added critical actions for OUTPUT_FOLDER configuration
5. Updated generate-test-cases prompt with output path instructions
6. Added comprehensive Output Management section to instructions.md (120+ lines)

### Agent Ready For Use
The agent is now production-ready with:
- Vietnamese language support with technical terms in English
- Automatic output folder creation and management
- Comprehensive error handling
- Clear user communication templates
- Validated YAML structure
