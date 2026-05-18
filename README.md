# emad-portfolio-management-hr-design
A professional portfolio and project hub for Emad Dawoud, combining graphic design, HR, management, web design, automation, and creative digital projects.
You are a senior React + TypeScript developer.

I want you to improve my Claude project by adding a professional “Skills” system.

First:
1. Inspect the full GitHub/project codebase.
2. Understand the folder structure.
3. Find the routing system.
4. Find the sidebar/navigation system.
5. Find existing UI components, auth, database, and storage patterns.
6. Do not break any existing pages.

Feature name:
Claude Skills Studio

Purpose:
Create a professional system where I can create, save, edit, test, organize, duplicate, import, and export AI skills/prompts for Claude.

Main pages to create:
- Skills Dashboard
- Create Skill
- Edit Skill
- Skill Detail
- Test Playground
- Import / Export
- Skill Settings

Add a sidebar item:
Claude Skills Studio

Skill data model:
Each skill must include:

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




You can also tell Claude this:

```text
Make this feature production-level, not demo-level. I want it to look like a real SaaS tool for managing Claude skills and reusable AI workflows.
