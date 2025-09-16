# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Xeenaa Village Picker** is a Minecraft Fabric mod for version 1.21.1 that provides an intuitive GUI for managing villager professions.

### Core Features
- **Right-click Interaction**: Players can right-click on any villager to open the profession selection GUI
- **Complete Profession List**: Displays all available professions including vanilla and modded professions
- **Profession Assignment**: Allows players to assign any available profession to the selected villager
- **Persistence**: Assigned professions persist through game sessions and work as intended by the game mechanics
- **Mod Compatibility**: Automatically detects and includes professions from other installed mods
- **Performance Optimized**: Built with efficiency in mind to minimize performance impact

### Technical Requirements
- **Minecraft Version**: 1.21.1
- **Mod Loader**: Fabric
- **Dependencies**: Fabric API
- **Java Version**: 21 (required for Minecraft 1.21.1)

## Working Methodology

This project follows a structured documentation approach with four key files:

1. **CLAUDE.md** (this file) - Contains project specifications, explanations, and guidance for Claude instances
2. **standards.md** - Documents all project code standards and conventions
3. **tasks.md** - Tracks tasks to be completed
4. **changelog.md** - Records all changes and decisions made during development

### Workflow Process

When working on this project, ALWAYS:

**Before any work:**
1. Read changelog.md to avoid repeating past issues
2. Check tasks.md to identify the next task and review previous task status
3. Review standards.md for current code conventions
4. Consult CLAUDE.md for project specifications and context

**During work:**
1. Follow all code standards defined in standards.md
2. Reference the current task from tasks.md

**After completing work:**
1. Update tasks.md - mark completed tasks and add any new tasks discovered
2. Update changelog.md with changes made and decisions taken
3. Update standards.md when new code patterns or conventions are established
4. Update CLAUDE.md if project specifications change

This methodology persists across all sessions - always maintain and reference these files when working on the project. Never skip checking these files.

## Development Notes

Since this is a new project, the specific build commands, testing framework, and architecture will be established as the codebase develops. When implementing features:

1. Check for any configuration files (package.json, requirements.txt, etc.) to understand the project setup
2. Look for build scripts or makefiles once they are added
3. Follow the established patterns as the codebase grows

## Project Structure

The project structure will be defined as development progresses. Based on the name, this appears to be a tool for selecting or managing villages in Minecraft.