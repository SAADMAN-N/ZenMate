# Employee Onboarding Builder - Specification

## Overview

Create a fully customizable employee onboarding experience builder similar in layout and style to the company onboarding UI shown in `company_onboarding`. This builder should empower HR teams to design their own onboarding flows with:

- Drag & drop flow construction
- Template-based quick-start options
- Step-by-step checkpoint creation and reordering

---

## Core Features

### 1. **Welcome Page (like company onboarding)**

- Headline: `Welcome to [CompanyName] 🎉`
- Subtext: `Let’s build your custom onboarding flow in a few easy steps.`
- Options:
  - "Use a Template" (with preview cards)
  - "Create from Scratch"
- Templates (Previewable):
  - Basic Onboarding
  - Remote Worker Pack
  - Cultural Warm-Up
  - Freelance Contractor
  - Tech Onboarding

---

### 2. **Builder Interface Layout**

| Section       | Function                                                 |
| ------------- | -------------------------------------------------------- |
| Left Sidebar  | Components to drag (Text, Input, File Upload, Date, etc) |
| Center Canvas | Shows current flow steps; editable, reorderable          |
| Right Sidebar | Configuration for selected step/component                |

#### Center Canvas (Checkpoints)

- Each checkpoint = a vertical card
- Each card is reorderable (drag up/down)
- Each has a name and list of components
- - Button: "Add Checkpoint"

#### Components Available:

- Text
- Input Field (Short/Long)
- Dropdown
- Checkbox
- Document Upload
- Signature Pad
- Date Picker
- Video Embed
- AI Answer Field
- Quiz Block
- Checklist

---

### 3. **Checkpoint Controls**

- Drag to reorder
- Click to rename
- Trash/delete checkpoint

---

### 4. **AI Features**

- **"Smart Flow Generator"**: Input job title → AI builds flow
- **Auto Suggest Fields**: Based on industry/company size
- **Auto Translate**: Localization support
- **Auto Quiz Builder**: Upload handbook → get questions

---

### 5. **Buttons & Flow**

- At bottom: ← Back / → Continue (matches UI of company onboarding)
- Top bar: Save, Preview, Publish

---

## Database Models (Suggested)

### `OnboardingFlow`

- id
- company_id
- name
- created_at
- updated_at

### `Checkpoint`

- id
- onboarding_flow_id
- title
- order_index

### `FormField`

- id
- checkpoint_id
- type (input, file, text, dropdown...)
- label
- required
- options (if dropdown)

---

## UX Details

- Dark mode UI (match existing branding)
- Rounded corners, card-based sections
- Previews for templates
- Consistent top progress bar (like onboarding)

---

## Notes

- This spec can be directly interpreted and developed by Cursor AI editor.
- Focus on flexibility + UX polish
- Follow same spacing, typography, and button layout as existing setup
