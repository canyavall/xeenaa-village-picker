# Tasks

## Task Tracking for Xeenaa Village Picker

### Current Implementation Tasks (Sequential Order)

#### Phase 1: Project Setup
**Task 1.1: Initialize Gradle Project** ✅ COMPLETED
- [x] Download and set up Fabric example mod template
- [x] Configure gradle.properties with mod metadata
- [x] Set Minecraft version to 1.21.1
- [x] Set Fabric loader and API versions
- [x] **Test**: Verify gradle build succeeds

**Task 1.2: Configure Project Structure** ✅ COMPLETED
- [x] Create package structure: com.xeenaa.villagepicker
- [x] Set up fabric.mod.json with mod metadata
- [x] Configure xeenaa_village_picker.mixins.json
- [x] Add Fabric API dependency to build.gradle
- [x] **Test**: Run client in dev environment

**Task 1.3: Setup Development Environment** ✅ COMPLETED
- [x] Configure IDE (IntelliJ IDEA/VSCode) - Created config files for both
- [x] Set up run configurations for client and server
- [x] Install Minecraft Development plugin - N/A (using Gradle tasks)
- [x] Configure hot reload for development
- [x] **Test**: Verify hot reload works

#### Phase 2: Core Mod Foundation
**Task 2.1: Create Main Mod Class** ✅ COMPLETED (Early - Done in Task 1.2)
- [x] Create XeenaaVillagePicker.java entry point
- [x] Implement ModInitializer interface
- [x] Add mod ID constant and logger
- [x] Register mod with Fabric loader
- [x] **Test**: Verify mod loads in game logs

**Task 2.2: Create Client Initializer** ✅ COMPLETED (Early - Done in Task 1.2)
- [x] Create XeenaaVillagePickerClient.java
- [x] Implement ClientModInitializer
- [x] Set up client-side event registration
- [x] Add client logger
- [x] **Test**: Verify client initialization

#### Phase 3: Entity Interaction System
**Task 3.1: Create Villager Interaction Mixin** ✅ COMPLETED
- [x] Create VillagerEntityMixin class
- [x] Add @Mixin annotation targeting VillagerEntity
- [x] Implement interactMob injection point
- [x] Add right-click detection logic
- [x] **Test**: Log interactions to console

**Task 3.2: Add Interaction Event Handler** ✅ COMPLETED
- [x] Create InteractionHandler utility class
- [x] Implement main hand check
- [x] Add player permission validation
- [x] Handle client-server side logic
- [x] **Test**: Verify single-player interaction

#### Phase 4: Profession Registry System
**Task 4.1: Create Profession Manager** ✅ COMPLETED
- [x] Create ProfessionManager singleton class
- [x] Implement profession collection from registry
- [x] Add method to get all professions
- [x] Include modded profession detection
- [x] **Test**: Log all detected professions

**Task 4.2: Create Profession Data Model** ✅ COMPLETED
- [x] Create ProfessionData class
- [x] Add fields: id, name, workstation, icon
- [x] Implement comparator for sorting
- [x] Add translation key support
- [x] **Test**: Verify data model population

#### Phase 5: GUI Implementation
**Task 5.1: Create Base Profession Screen**
- [ ] Create ProfessionSelectionScreen extends Screen
- [ ] Add basic screen layout
- [ ] Implement init() and render() methods
- [ ] Add close button functionality
- [ ] **Test**: Open screen with command

**Task 5.2: Create Profession List Widget**
- [ ] Create ProfessionListWidget extends EntryListWidget
- [ ] Implement ProfessionEntry inner class
- [ ] Add scrolling functionality
- [ ] Add hover effects
- [ ] **Test**: Display all professions in list

**Task 5.3: Add Profession Icons**
- [ ] Load workstation block icons
- [ ] Create icon rendering method
- [ ] Add fallback for missing icons
- [ ] Implement icon caching
- [ ] **Test**: Verify icon display

**Task 5.4: Implement Search Functionality**
- [ ] Add TextFieldWidget for search
- [ ] Implement filter logic
- [ ] Add real-time search update
- [ ] Support localized name search
- [ ] **Test**: Search for specific professions

**Task 5.5: Add Profession Details Panel**
- [ ] Create details panel component
- [ ] Display profession name and description
- [ ] Show required workstation
- [ ] Add trades preview (optional)
- [ ] **Test**: Verify details update on selection

#### Phase 6: Networking System
**Task 6.1: Create Network Packets**
- [ ] Create OpenGuiPacket (S2C)
- [ ] Create SelectProfessionPacket (C2S)
- [ ] Create ProfessionUpdatePacket (S2C)
- [ ] Register packet handlers
- [ ] **Test**: Packet serialization/deserialization

**Task 6.2: Implement Client-Server Communication**
- [ ] Add server-side packet receivers
- [ ] Implement client-side packet handlers
- [ ] Add packet validation
- [ ] Handle disconnection gracefully
- [ ] **Test**: Verify in local multiplayer

#### Phase 7: Profession Assignment Logic
**Task 7.1: Implement Profession Change System**
- [ ] Create VillagerProfessionHelper class
- [ ] Add method to change profession
- [ ] Handle workstation association
- [ ] Preserve villager level if applicable
- [ ] **Test**: Change profession in-game

**Task 7.2: Add Profession Validation**
- [ ] Check if villager can have profession
- [ ] Validate baby villager restrictions
- [ ] Handle nitwit special case
- [ ] Add zombie villager check
- [ ] **Test**: Try invalid assignments

**Task 7.3: Implement Persistence**
- [ ] Save profession to NBT data
- [ ] Load profession on world load
- [ ] Handle chunk unload/reload
- [ ] Sync with client on join
- [ ] **Test**: Restart world and verify

#### Phase 8: Edge Cases & Compatibility
**Task 8.1: Handle Special Villager Types**
- [ ] Support wandering traders
- [ ] Handle illagers appropriately
- [ ] Add baby villager restrictions
- [ ] Support modded villager variants
- [ ] **Test**: All villager types

**Task 8.2: Add Mod Compatibility Layer**
- [ ] Detect other villager mods
- [ ] Handle custom profession types
- [ ] Add compatibility with Guards mod
- [ ] Support MCA Reborn if present
- [ ] **Test**: With popular villager mods

#### Phase 9: Polish & Optimization
**Task 9.1: Add Visual Feedback**
- [ ] Add success/failure messages
- [ ] Implement sound effects
- [ ] Add particle effects on change
- [ ] Create smooth GUI transitions
- [ ] **Test**: User experience flow

**Task 9.2: Performance Optimization**
- [ ] Implement profession caching
- [ ] Add lazy loading for icons
- [ ] Optimize network packets
- [ ] Profile and fix bottlenecks
- [ ] **Test**: With 100+ villagers

#### Phase 10: Configuration & API
**Task 10.1: Add Configuration System**
- [ ] Create config file structure
- [ ] Add permission levels setting
- [ ] Add GUI customization options
- [ ] Implement config reload command
- [ ] **Test**: Config changes apply

**Task 10.2: Create Public API**
- [ ] Define API interfaces
- [ ] Add events for other mods
- [ ] Document API methods
- [ ] Create example implementation
- [ ] **Test**: External mod integration

#### Phase 11: Documentation & Release
**Task 11.1: Create Documentation**
- [ ] Write comprehensive README.md
- [ ] Add wiki pages
- [ ] Create mod showcase video script
- [ ] Add in-game help/tutorial
- [ ] **Test**: Follow own documentation

**Task 11.2: Prepare for Release**
- [ ] Run full test suite
- [ ] Fix all known bugs
- [ ] Optimize final build
- [ ] Create release notes
- [ ] **Test**: Clean install test

### Completed Tasks
- [x] Create CLAUDE.md with workflow documentation
- [x] Define project specifications (Fabric mod for 1.21.1)
- [x] Research Fabric 1.21.1 best practices
- [x] Create standards.md with Fabric coding standards
- [x] Create tasks.md for task tracking
- [x] Create changelog.md for change documentation

### Future Enhancements
- [ ] Add configuration file for mod settings
- [ ] Implement hotkey for quick profession assignment
- [ ] Add profession locking feature
- [ ] Create profession templates/presets
- [ ] Add statistics tracking
- [ ] Implement undo/redo functionality
- [ ] Add sound effects and particles
- [ ] Create API for other mods

---
*Last Updated: Project Definition - Fabric 1.21.1 Villager Profession Selector*