# Agent Creation Complete! 🎉

## Agent Summary

- **Name:** TestGen - QA Assistant
- **Type:** Expert Agent with Sidecar
- **Purpose:** Generate comprehensive test cases from UI screenshots following 3-tier methodology with strict Excel template adherence
- **Status:** ✅ Ready for installation
- **Created:** 2026-01-21

---

## Agent Capabilities

### UI Element Detection
- Buttons, Forms, Navigation
- Textboxes, Comboboxes, Checkboxes
- Title, Pagination

### Test Case Generation (3-Tier)
1. **TIER 1: General Interface** (7 test cases)
   - Title, focus, fields, header, footer check
   - Layout, font, color validation
   - Tab/Shift-Tab navigation
   - Enter button behavior
   - Zoom in/out functionality

2. **TIER 2: Validate** (Element-specific)
   - Textbox: placeholder, character input, boundaries, format
   - Dropdown/Combobox: options, selection, search
   - Button: visual states, behavior
   - Checkbox: state management

3. **TIER 3: Function** (Success + Failed)
   - Success cases: valid flows, alternative paths
   - Failed cases: required validation, invalid data, internet check, server errors

### Excel Operations
- Template loading with structure preservation
- Common test cases integration
- Excel MCP mandatory access
- Output with exact formatting (colors, formulas, structure)

---

## File Locations

### Agent Files
- **Agent YAML:** `C:\Users\Windows\Desktop\Test Agent\test-case-generator\test-case-generator.agent.yaml`
- **Sidecar Instructions:** `C:\Users\Windows\Desktop\Test Agent\test-case-generator\test-case-generator-sidecar\instructions.md`
- **Sidecar README:** `C:\Users\Windows\Desktop\Test Agent\test-case-generator\test-case-generator-sidecar\README.md`

### Template Files
- **Template:** `C:\Users\Windows\Desktop\Test Agent\excel_files\Template_TCs_web.xlsx`
- **Common Cases:** `C:\Users\Windows\Desktop\Test Agent\excel_files\common-testcase.xlsx`

---

## Commands Reference

| Code | Command | Description |
|------|---------|-------------|
| **IN** | initialize | One-click setup: check MCP → load common cases → validate template |
| **GT** | generate-tests | Generate test cases from UI screenshot |
| **VT** | validate-template | Validate Excel template structure |
| **LC** | load-common | Load common test case patterns |
| **CM** | check-mcp | Check MCP access status |
| **HE** | help | Show help and usage guide |

---

## Installation

### Module Structure

Create a custom BMAD module with this structure:

```
my-test-agents/
├── module.yaml              # Contains: unitary: true
└── agents/
    └── test-case-generator/
        ├── test-case-generator.agent.yaml
        └── _memory/
            └── test-case-generator-sidecar/
                ├── instructions.md
                └── README.md
```

### Installation Steps

1. **Create module folder:**
   ```bash
   mkdir my-test-agents
   cd my-test-agents
   ```

2. **Create module.yaml:**
   ```yaml
   unitary: true
   ```

3. **Create agents directory structure:**
   ```bash
   mkdir -p agents/test-case-generator/_memory
   ```

4. **Copy agent files:**
   ```bash
   cp test-case-generator.agent.yaml agents/test-case-generator/
   cp -r test-case-generator-sidecar/ agents/test-case-generator/_memory/
   ```

5. **Install via BMAD:**
   - New projects: BMAD installer will prompt for local custom modules
   - Existing projects: Use "Modify BMAD Installation" to add module

### Full Documentation

📖 [BMAD Custom Content Installation Guide](https://github.com/bmad-code-org/BMAD-METHOD/blob/main/docs/modules/bmb-bmad-builder/custom-content-installation.md#standalone-content-agents-workflows-tasks-tools-templates-prompts)

---

## Quick Start

### First Interaction

1. **Initialize the agent:**
   ```
   IN
   ```
   Agent will check MCP, load common cases, and validate template.

2. **Generate test cases:**
   - Upload UI screenshot
   - Run command: `GT`
   - Agent analyzes screenshot and generates test cases

3. **Output:**
   - Excel file with test cases following 3-tier structure
   - All template formatting preserved (colors, formulas, structure)

### Typical Workflow

```
User: IN
Agent: ✓ MCP access confirmed
       ✓ Common test cases loaded (20 patterns)
       ✓ Template validated (5 sheets)
       → Agent ready!

User: [Upload screenshot of login form] GT
Agent: Analyzing UI...
       Identified: 2 textboxes, 1 checkbox, 2 buttons
       
       Generated:
       - TIER 1: 7 General Interface test cases
       - TIER 2: 12 Validate test cases (textbox boundaries, button states)
       - TIER 3: 8 Function test cases (3 success, 5 failed including internet check)
       
       Excel file: test-cases-login-form-2026-01-21.xlsx
       Download ready!
```

---

## Technical Details

### Agent Type
- **Classification:** Expert Agent
- **Module:** stand-alone
- **hasSidecar:** true

### Persona
- **Role:** QA Test Case Specialist
- **Identity:** Senior QA Engineer
- **Communication:** Vietnamese, structured, professional
- **Principles:** 5 expert principles (QA wisdom, template adherence, 3-tier hierarchy, MCP mandatory, common foundation)

### Critical Actions (Startup)
1. Load sidecar instructions
2. Check Excel MCP availability (blocking)
3. Enforce MCP-only file access

### Exclusions
Agent does NOT generate:
- Security test cases
- Performance & loading tests
- Error handling tests
- Browser compatibility tests
- Test execution notes
- Preconditions for dependent screens

---

## Support

### Template Requirements
- Excel template must exist at specified path
- Common test cases file must exist
- Excel MCP must be available

### Prerequisites
- Excel MCP integration enabled
- Template files accessible
- BMAD installation complete

### Troubleshooting
- If MCP unavailable: Agent will stop and request permission
- If template not found: Run [VT] to validate template path
- If common cases not loaded: Run [LC] to reload

---

## Created With

- **BMAD Agent Builder** (BMB)
- **Workflow:** Agent Creation (Create)
- **Date:** 2026-01-21
- **Status:** Complete and ready for installation

---

**🎉 Congratulations on creating your custom BMAD agent!**
