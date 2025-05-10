# AtomHR Onboarding Implementation Checklist

## Overview

This document outlines the implementation plan for the company onboarding process in AtomHR, with a focus on the role management system and related features.

## UI/UX Requirements

- ✅ Dark mode styling (Apple-inspired)
- ✅ Sleek animations and smooth transitions between steps
- ✅ Progress indicator showing steps (Company Info → Roles → Invite Employees)
- ✅ Clean cards, glowing buttons
- ✅ Role selection with visual indicators
- ✅ Modal forms for quick inline creation

## Database Models (Prisma)

- ✅ Role Model

  - ✅ name (string)
  - ✅ department (string)
  - ✅ level (string - Junior/Mid/Senior/Lead)
  - ✅ default_location (string)
  - ✅ base_salary_range (min, max)
  - ✅ relations to Job and Employee

- ✅ Job Model

  - ✅ Update to include reference to Role

- ✅ Employee Model

  - ✅ Update to include reference to Role

- ✅ Invitation Model
  - ✅ Links to Role, Employee, and Company

## Company Onboarding Flow Implementation

### New Public Onboarding Flow

- ✅ Create public company setup page that doesn't require authentication
- ✅ Implement token-based security for company setup
- ✅ Create API endpoints for company creation without a user account
- ✅ Update landing page with link to company setup

### Step 1: Company Info

- ✅ Create company info form component
  - ✅ Company name
  - ✅ Industry
  - ✅ Company size
  - ✅ Location
  - ✅ Logo upload
- ✅ Create API endpoint to save company info
- ✅ Implement form validation
- ✅ Add animations for form transitions

### Step 2: Roles

- ✅ Create role management interface
  - ✅ Default role selection
  - ✅ Custom role creation form
    - ✅ Role Name (string)
    - ✅ Department (string)
    - ✅ Level (string dropdown)
    - ✅ Location (string)
  - ✅ Display selected roles
- ✅ Create API endpoints for role management
- ✅ Implement form validation
- ✅ Add animations for form transitions

### Step 3: Invite Employees

- ✅ Create employee invitation interface
  - ✅ Email input (single or bulk)
  - ✅ Role assignment dropdown
  - ✅ Custom message
  - ✅ Send invitation button
- ✅ Create API endpoint for sending invitations
- ✅ Implement form validation
- ✅ Add animations for form transitions

## Employee Onboarding Flow

### Invitation Acceptance

- ✅ Create invitation verification endpoint
- ✅ Create invitation acceptance page
- ✅ Implement account creation upon invitation acceptance
- ✅ Auto-assign role based on invitation

### Employee Onboarding

- ✅ Create database models for customizable onboarding
  - ✅ OnboardingTemplate model
  - ✅ OnboardingStep model
  - ✅ FormComponent model
  - ✅ OnboardingResponse model
  - ✅ ComponentResponse model
- ✅ Create API endpoints for template management
  - ✅ Create template
  - ✅ Update template
  - ✅ Delete template
  - ✅ Get templates
  - ✅ Get default templates
- ✅ Create form builder components
  - ✅ FormBuilder context
  - ✅ Main FormBuilder component
  - ✅ StepsSidebar component
  - ✅ ComponentPalette component
- ✅ Create template management pages
  - ✅ Templates list page
  - ✅ Create template page
  - ✅ Edit template page
- ✅ Create form preview component
- ✅ Create properties panel component
- ✅ Create employee onboarding flow
  - ✅ Create API endpoints for onboarding responses
  - ✅ Create employee onboarding dashboard page
  - ✅ Create onboarding flow page with step navigation
  - ✅ Create form component renderer
- ✅ Implement response storage and progress tracking

## Role Management System

### 1. Role Creation (Admin Only)

- ✅ Backend API route /api/setup/roles to create new roles
- ✅ Role form with all required fields
- ✅ Display existing roles with selection options

### 2. Assign Role When Creating Job

- [ ] Update Job Creation form with role dropdown
- [ ] Add option to create new role inline ("+ New Role")
- [ ] Link selected role to job in database

### 3. Assign Role on Hiring

- [ ] Implement automatic employee creation when candidate is hired
- [ ] Assign the same roleId from the Job to the Employee
- [ ] Link employee to roleId, managerId, and department

### 4. Manual Role Update in Employee Profile

- [ ] Add role management to /dashboard/employees/[id]
- [ ] Create dropdown to change roles
- [ ] Implement PATCH /api/employees/[id] endpoint
- [ ] Add history logging for role changes

### 5. Permissions (Internal Use)

- [ ] Create permission mapping system
  - [ ] Admin: can manage roles, employees, jobs
  - [ ] HR: can assign roles, create jobs
  - [ ] Manager: view team, submit performance reviews
  - [ ] Employee: view self only
- [ ] Implement middleware-based route protection (optional)

## Implementation Approach

- Focus on one task at a time
- Break larger tasks into smaller, manageable subtasks
- Store all data in the database
- Follow Apple-inspired dark mode styling
- Ensure smooth animations and transitions
