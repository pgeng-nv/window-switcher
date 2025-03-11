# Window Switcher - Development Guidelines

## Build Commands
- `cargo build` - Build the project
- `cargo build --release` - Build optimized release version
- `cargo run` - Run in debug mode
- `cargo run --release` - Run optimized version
- `cargo test` - Run all tests
- `cargo test <test_name>` - Run specific test
- `cargo clippy` - Lint the code
- `cargo fmt` - Format code

## Code Style Guidelines
- **Error Handling**: Use `anyhow` for app-level errors; use `windows::core::Result` for Win32 API calls
- **Win32 API**: Always wrap API calls in `unsafe` blocks and use `check_error()` utility
- **Imports**: Group standard library, external crates, and internal modules
- **Naming**: Use snake_case for functions/variables, CamelCase for types, SCREAMING_SNAKE_CASE for constants
- **Module Structure**: Follow the existing module hierarchy with utils for Windows-specific helpers
- **Comments**: Document unsafe blocks with rationale; document public functions/types
- **UI Elements**: Use alert macro for user-facing messages
- **Registry Editing**: Use the utils::regedit module for registry operations
- **Windows Features**: Use proper handle wrappers with appropriate cleanup

New code should match existing patterns and properly handle Windows resources.