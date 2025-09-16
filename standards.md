# Code Standards

## Project Standards and Conventions

This document defines the coding standards and conventions for the Xeenaa Village Picker Fabric mod.

### General Principles

- Code clarity and readability take precedence over cleverness
- Follow established patterns within the codebase
- Document complex logic and non-obvious decisions
- Prioritize performance and compatibility with other mods
- Use Fabric API events over direct mixins when possible

### File Organization

```
src/main/
├── java/com/xeenaa/villagepicker/
│   ├── XeenaaVillagePicker.java       # Main mod class
│   ├── client/
│   │   ├── gui/                       # GUI screens and widgets
│   │   └── render/                    # Rendering utilities
│   ├── mixin/                         # Mixin classes
│   │   ├── client/                    # Client-side mixins
│   │   └── common/                    # Common mixins
│   ├── network/                       # Networking packets
│   ├── util/                          # Utility classes
│   └── registry/                      # Registries and initialization
└── resources/
    ├── fabric.mod.json                 # Mod metadata
    ├── xeenaa_village_picker.mixins.json  # Mixin configuration
    └── assets/xeenaa_village_picker/   # Assets (textures, lang, etc.)
```

### Naming Conventions

- **Packages**: lowercase, use `com.xeenaa.villagepicker`
- **Classes**: PascalCase (e.g., `ProfessionSelectionScreen`)
- **Interfaces**: PascalCase with descriptive names
- **Methods**: camelCase (e.g., `openProfessionGui`)
- **Constants**: UPPER_SNAKE_CASE
- **Mixins**: Target class name + "Mixin" suffix (e.g., `VillagerEntityMixin`)

### Code Style

- **Java Version**: Java 21 (required for Minecraft 1.21.1)
- **Indentation**: 4 spaces (no tabs)
- **Line Length**: Max 120 characters
- **Brackets**: Opening brace on same line
- **Comments**: Use Javadoc for public APIs, inline comments for complex logic

### Mixin Best Practices

1. **Prefer Events Over Mixins**: Use Fabric API events when available
2. **Mixin Organization**:
   - Use `.mixin` package suffix
   - Separate client and common mixins
   - One mixin per target class
3. **Injection Points**:
   - Use `@Inject` with `cancellable = true` for interactions
   - Prefer `@Local` over `LocalCapture` for variable capture
   - Use MixinExtras annotations for cleaner code
4. **Performance**:
   - Minimize injection points
   - Avoid reflection, use `@Shadow` instead
   - No double casting of `this`

### Entity Interaction Pattern

```java
@Mixin(VillagerEntity.class)
public class VillagerEntityMixin {
    @Inject(method = "interactMob", at = @At("HEAD"), cancellable = true)
    private void onInteract(PlayerEntity player, Hand hand, CallbackInfoReturnable<ActionResult> cir) {
        if (player.world.isClient && hand == Hand.MAIN_HAND) {
            // Open GUI
            cir.setReturnValue(ActionResult.SUCCESS);
        }
    }
}
```

### GUI Development Standards

1. **Screen Classes**: Extend `Screen` or `HandledScreen`
2. **Widgets**: Use Fabric API widgets when possible
3. **Rendering**: Use immediate mode rendering for performance
4. **Networking**: Use Fabric networking API for client-server communication

### Performance Guidelines

1. **Lazy Loading**: Load profession data only when needed
2. **Caching**: Cache profession registry lookups
3. **Event Handling**: Return early from event handlers when not applicable
4. **Memory**: Use FerriteCore-compatible patterns
5. **Networking**: Minimize packet size and frequency

### Testing Standards

- Unit tests for utility classes
- Integration tests for mixins
- Manual testing with popular mod combinations:
  - Sodium + Lithium + Krypton
  - Other villager-related mods

### Documentation Requirements

- Javadoc for all public APIs
- README with installation and usage instructions
- Comments for complex mixin logic
- Changelog for all releases

### Version Control

- **Branch Strategy**: main (stable), develop (active development)
- **Commit Messages**: Descriptive, present tense
- **Tags**: Use semantic versioning (e.g., v1.0.0)

### Compatibility Standards

1. **Mod Compatibility**:
   - Test with major performance mods (Sodium, Lithium, etc.)
   - Handle modded professions gracefully
   - Use Fabric API for maximum compatibility
2. **Version Support**:
   - Target Minecraft 1.21.1 specifically
   - Use Fabric Loader 0.16.7+
   - Fabric API 0.116.0+

---
*Last Updated: Project initialization with Fabric 1.21.1 standards*