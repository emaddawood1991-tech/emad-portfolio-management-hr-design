# Claude Skills Studio — Product Specification

## Purpose

Create a professional system where users can create, save, edit, test, organize, duplicate, import, and export AI skills and prompts for Claude.

## Discovery Requirements

Before implementation:

1. Inspect the full project codebase.
2. Understand the folder structure.
3. Find the routing system.
4. Find the sidebar and navigation system.
5. Identify existing UI components, authentication, database, and storage patterns.
6. Preserve all existing pages and workflows.

## Main Views

- Skills Dashboard
- Create Skill
- Edit Skill
- Skill Detail
- Test Playground
- Import / Export
- Skill Settings

Add a sidebar item named **Claude Skills Studio**.

## Data Model

```ts
export type SkillStatus = "draft" | "active" | "archived";
export type SkillVisibility = "private" | "team" | "public";

export interface SkillInputField {
  id: string;
  name: string;
  label: string;
  type: "text" | "textarea" | "select" | "number" | "date" | "file";
  required: boolean;
  placeholder?: string;
  defaultValue?: string;
  options?: string[];
}

export interface ClaudeSkill {
  id: string;
  title: string;
  shortDescription: string;
  category: string;
  tags: string[];
  skillType: string;
  systemPrompt: string;
  userPromptTemplate: string;
  inputFields: SkillInputField[];
  outputFormat: "plain_text" | "markdown" | "json" | "table" | "bilingual_ar_en";
  tone: string;
  language: string;
  status: SkillStatus;
  visibility: SkillVisibility;
  version: number;
  exampleInput?: Record<string, string>;
  exampleOutput?: string;
  usageCount: number;
  createdBy?: string;
  createdAt: string;
  updatedAt: string;
}
```

## Product Standard

Build this as a production-level SaaS feature rather than a demo. Prioritize maintainability, authentication, durable data storage, versioning, responsive UX, accessibility, and safe prompt handling.
