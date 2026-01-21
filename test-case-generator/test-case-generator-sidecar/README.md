# Test Case Generator Sidecar

This folder stores persistent instructions and workflows for the **Test Case Generator** Expert agent.

---

## Purpose

Provides comprehensive protocols for generating test cases from UI screenshots, following strict 3-tier methodology (General Interface → Validate → Function) with mandatory Excel template adherence.

---

## Files

### `instructions.md`
Complete agent protocols including:
- UI element detection rules (buttons, forms, textboxes, comboboxes, checkboxes, navigation, pagination, titles)
- 3-tier test case generation structure
- Excel template adherence requirements
- Common test cases integration
- MCP access requirements
- Quality assurance principles

---

## Runtime Access

After BMAD installation, this folder will be accessible at:
```
{project-root}/_bmad/_memory/test-case-generator-sidecar/
```

---

## Agent Type

**Expert Agent** with:
- Sidecar folder for complex protocols
- Stand-alone module (independent operation)
- Excel MCP integration (mandatory)
- Vietnamese language support

---

## Test Case Structure

### TIER 1: General Interface (7 cases)
1. Comprehensive interface check (title, focus, fields, header, footer)
2. Layout, font, color validation
3. Tab button navigation
4. Shift-Tab reverse navigation
5. Enter button behavior
6. Zoom in/out functionality
7. Responsive behavior

### TIER 2: Validate (per element)
- Textbox: placeholder, character input, boundaries, format
- Dropdown/Combobox: options, selection, search
- Button: visual states, behavior
- Checkbox: state management, validation

### TIER 3: Function
- Success cases: Valid flows, alternative paths
- Failed cases: Required field validation, invalid data, internet check, server errors

---

## Template Files

- **Template**: `C:\Users\Windows\Desktop\Test Agent\excel_files\Template_TCs_web.xlsx`
- **Common Cases**: `C:\Users\Windows\Desktop\Test Agent\excel_files\common-testcase.xlsx`

---

## Exclusions

Agent does NOT generate:
- Security test cases
- Performance & loading tests
- Error handling tests
- Browser compatibility tests
- Test execution notes
- Preconditions for dependent screens

---

## Agent Commands

| Code | Command | Description |
|------|---------|-------------|
| **IN** | initialize | One-click setup: check MCP → load common → validate template |
| **GT** | generate-tests | Generate test cases from screenshot |
| **VT** | validate-template | Validate template structure |
| **LC** | load-common | Load common test case patterns |
| **CM** | check-mcp | Check MCP access status |
| **HE** | help | Show usage guide |

---

## Created

- Date: 2026-01-21
- Agent Type: Expert
- Module: stand-alone
- MCP Requirement: Excel MCP (mandatory)
