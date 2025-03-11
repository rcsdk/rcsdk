Bash Script Requirements

GRAPHIC -
Ultimate Bash Script Requirements
Visual Design & Aesthetics (Primary Focus)

    Luxurious Dark Background Design: Implement rich, deep background colors optimized for dark terminals
    Jazz-Inspired Pastel Palette: Use sophisticated pastel tones with careful contrast ratios for readability
    Visual Hierarchy: Employ color, weight, and spacing to create clear visual organization of information
    Typography Enhancements: Utilize Unicode for rich typography where standard terminals support it
    Borders and Panels: Create elegant bordered sections using Unicode box-drawing characters
    Visual Rhythm: Establish consistent visual patterns and spacing throughout output
    Whitespace Utilization: Strategic use of whitespace to create breathing room and emphasis
    Icon Integration: Incorporate Unicode symbols and icons as visual markers for different message types
    Color Psychology: Apply color theory principles to convey status, urgency, and importance
    Artistic Touches: Add subtle artistic elements that don't interfere with functionality

Interactive Elements

    Premium Progress Bars: Implement multi-segment progress indicators with gradient coloring
    Designer Spinners: Create elegant terminal spinners with multiple artistic styles
    Animated Transitions: Smooth transitions between script phases using subtle animations
    Typewriter Effects: Professional typewriter-style text for important announcements
    Interactive Menus: Visually refined select menus with highlight effects
    Confirmation Dialogs: Styled dialog boxes for confirmations and important choices
    Status Dashboards: Live-updating dashboards for complex operations
    Micro-Animations: Subtle movement to indicate activity without distraction
    Sound Integration: Optional subtle terminal bell usage for critical alerts
    Visual Feedback: Immediate visual feedback for user actions and script progress

Best Practices

    Check Before Acting: Verify state before performing destructive actions
    Error Handling: Implement comprehensive error trapping and recovery
    Input Validation: Rigorously validate all input with descriptive error messages
    Secure Coding: Use environment variables and secure credential storage
    Modularity: Create function libraries for maintainable, reusable code
    Documentation: Include rich in-line documentation with visual formatting

Organization

    Logical Structure: Organize code with clear section demarcation
    Visual Dividers: Implement visually distinct section separators
    Self-Documenting Code: Use descriptive naming conventions throughout
    Component Architecture: Structure script as interconnected components

Efficiency

    Performance Optimization: Balance visual elements with execution speed
    Resource Management: Minimize system impact while maximizing aesthetic appeal
    Execution Branches: Optimize execution paths for different scenarios
    Caching Mechanisms: Cache results of expensive operations for reuse

Logging

    Styled Logging: Create visually distinct log entries by type and severity
    Hierarchical Logs: Organize logs with visual nesting and relationships
    Timeline Visualization: Show operation sequence with visual timeline elements
    Executive Summary: Generate a visually stunning operation summary
    Visual Metrics: Display key metrics with appropriate visual representations

Documentation

    Styled Help System: Create a comprehensive, visually appealing help system
    Visual Examples: Include stylized examples of command usage
    Quick Reference: Provide abbreviated command reference with visual cues
    Interactive Documentation: Allow exploration of documentation sections

Script Header Template

#!/usr/bin/env bash
# ╔══════════════════════════════════════════════════════════════════════════════╗
# ║ [SCRIPT_NAME]                                                                ║
# ║ A sophisticated tool for [PURPOSE]                                           ║
# ║                                                                              ║
# ║ Version: 1.0.0                                                               ║
# ║ Author:  [AUTHOR]                                                            ║
# ║ Created: [DATE]                                                              ║
# ║                                                                              ║
# ║ Usage:   ./[SCRIPT_NAME] [OPTIONS]                                           ║
# ╚══════════════════════════════════════════════════════════════════════════════╝

# ---- Color & Style Definitions ----
# Define our sophisticated color palette
readonly RESET="\033[0m"
readonly BLACK="\033[38;5;0m"
readonly DARK_BLUE="\033[38;5;24m"
readonly BLUE="\033[38;5;39m"
readonly LIGHT_BLUE="\033[38;5;117m"
readonly CYAN="\033[38;5;51m"
readonly TEAL="\033[38;5;37m"
readonly GREEN="\033[38;5;35m"
readonly LIGHT_GREEN="\033[38;5;121m"
readonly YELLOW="\033[38;5;221m"
readonly GOLD="\033[38;5;178m"
readonly ORANGE="\033[38;5;208m"
readonly RED="\033[38;5;196m"
readonly MAGENTA="\033[38;5;201m"
readonly PURPLE="\033[38;5;93m"
readonly PINK="\033[38;5;219m"
readonly GRAY="\033[38;5;245m"
readonly LIGHT_GRAY="\033[38;5;250m"
readonly WHITE="\033[38;5;255m"

# Background colors
readonly BG_BLACK="\033[48;5;0m"
readonly BG_DARK_BLUE="\033[48;5;24m"
readonly BG_BLUE="\033[48;5;39m"
readonly BG_DARK_GRAY="\033[48;5;237m"
readonly BG_GRAY="\033[48;5;240m"

# Text styles
readonly BOLD="\033[1m"
readonly DIM="\033[2m"
readonly ITALIC="\033[3m"
readonly UNDERLINE="\033[4m"
readonly BLINK="\033[5m"
readonly REVERSE="\033[7m"
readonly HIDDEN="\033[8m"

# Define theme-specific styles for message types
readonly STYLE_HEADER="${BOLD}${BLUE}"
readonly STYLE_SUCCESS="${GREEN}"
readonly STYLE_WARNING="${YELLOW}"
readonly STYLE_ERROR="${RED}"
readonly STYLE_INFO="${CYAN}"
readonly STYLE_DEBUG="${GRAY}"
readonly STYLE_PROMPT="${BOLD}${MAGENTA}"
readonly STYLE_EMPHASIS="${BOLD}${WHITE}"
readonly STYLE_DEEMPHASIS="${DIM}${LIGHT_GRAY}"

Comprehensive Testing & Error-Proofing

Please deliver a fully tested, visually stunning, and functionally flawless version of [script_name] that handles all possible execution scenarios:
Core Implementation Requirements
Visual Elements Library

    Create reusable functions for all visual components
    Implement a consistent theming system throughout
    Design visual elements that convey meaning beyond aesthetics
    Ensure all visual elements enhance rather than detract from usability

# ---- Visual Elements Library ----

# Function: Draw a stylish header box
draw_header() {
    local title="$1"
    local width=80
    local padding=$(( (width - ${#title} - 2) / 2 ))
    local padding_right=$padding
    
    # If odd length, add extra space on right
    if (( (width - ${#title} - 2) % 2 == 1 )); then
        padding_right=$((padding + 1))
    fi
    
    echo -e "${BLUE}╔$(printf '═%.0s' $(seq 1 $((width - 2))))╗${RESET}"
    echo -e "${BLUE}║${RESET}$(printf ' %.0s' $(seq 1 $padding))${BOLD}${WHITE}${title}${RESET}$(printf ' %.0s' $(seq 1 $padding_right))${BLUE}║${RESET}"
    echo -e "${BLUE}╚$(printf '═%.0s' $(seq 1 $((width - 2))))╝${RESET}"
}

# Function: Draw a stylish progress bar
draw_progress_bar() {
    local percent=$1
    local width=${2:-50}
    local completed=$((percent * width / 100))
    local remaining=$((width - completed))
    
    echo -ne "${BLUE}[${CYAN}"
    printf '█%.0s' $(seq 1 $completed)
    echo -ne "${GRAY}"
    printf '▒%.0s' $(seq 1 $remaining)
    echo -e "${BLUE}] ${WHITE}${percent}%${RESET}"
}

# Function: Animated spinner with color cycling
spinner() {
    local pid=$1
    local message="${2:-Working...}"
    local spin_chars=('⣾' '⣽' '⣻' '⢿' '⡿' '⣟' '⣯' '⣷')
    local colors=("$BLUE" "$CYAN" "$TEAL" "$GREEN" "$YELLOW" "$ORANGE" "$RED" "$MAGENTA" "$PURPLE")
    
    echo -ne "${STYLE_INFO}${message} ${RESET}"
    
    local i=0
    while kill -0 $pid 2>/dev/null; do
        local color_index=$((i % ${#colors[@]}))
        echo -ne "${colors[$color_index]}${spin_chars[$i % 8]}${RESET}\r"
        sleep 0.1
        echo -ne "${STYLE_INFO}${message} ${RESET}"
        ((i++))
    done
    
    echo -e "${STYLE_SUCCESS}${message} Complete ${RESET}"
}

# Function: Print text with typewriter effect
typewriter() {
    local text="$1"
    local delay=${2:-0.03}
    
    for ((i=0; i<${#text}; i++)); do
        echo -n "${text:$i:1}"
        sleep $delay
    done
    echo
}

# Function: Print a styled message box
message_box() {
    local message="$1"
    local style=${2:-$STYLE_INFO}
    local width=${3:-80}
    
    local lines=()
    local current_line=""
    local word=""
    
    # Word wrap to fit width
    for word in $message; do
        if (( ${#current_line} + ${#word} + 1 <= width - 4 )); then
            if [[ -z "$current_line" ]]; then
                current_line="$word"
            else
                current_line="$current_line $word"
            fi
        else
            lines+=("$current_line")
            current_line="$word"
        fi
    done
    
    # Add the last line if not empty
    if [[ -n "$current_line" ]]; then
        lines+=("$current_line")
    fi
    
    # Draw the box
    echo -e "${BLUE}┌$(printf '─%.0s' $(seq 1 $((width - 2))))┐${RESET}"
    
    for line in "${lines[@]}"; do
        local padding_right=$((width - ${#line} - 4))
        echo -e "${BLUE}│${RESET} ${style}${line}${RESET}$(printf ' %.0s' $(seq 1 $padding_right)) ${BLUE}│${RESET}"
    done
    
    echo -e "${BLUE}└$(printf '─%.0s' $(seq 1 $((width - 2))))┘${RESET}"
}

Handle All Errors Comprehensively

    Create visually distinct error messages by severity
    Implement error recovery with styled options
    Design informative error diagnostics with visual hierarchy
    Apply consistent error styling throughout the script

Implement Executive Summary

    Design a visually stunning summary report
    Include relevant metrics with appropriate visualization
    Create a section for next steps with visual emphasis
    Ensure the summary provides a complete picture of script execution

# Function: Display a beautiful executive summary
executive_summary() {
    local task="$1"
    local status="$2"
    local items_processed="$3"
    local items_modified="$4"
    local warnings="$5"
    local errors="$6"
    local next_steps="$7"
    local time_elapsed="$8"
    
    # Status indicator
    local status_color="$STYLE_SUCCESS"
    [[ "$status" != "Success" ]] && status_color="$STYLE_ERROR"
    
    echo
    echo -e "${BLUE}╔════════════════════════════════════════════════════════════════════╗${RESET}"
    echo -e "${BLUE}║${BOLD}${WHITE}                        EXECUTIVE SUMMARY                        ${RESET}${BLUE}║${RESET}"
    echo -e "${BLUE}╠════════════════════════════════════════════════════════════════════╣${RESET}"
    echo -e "${BLUE}║${RESET} ${BOLD}Task:${RESET}        ${WHITE}$task${RESET}$(printf ' %.0s' $(seq 1 $((47 - ${#task})))) ${BLUE}║${RESET}"
    echo -e "${BLUE}║${RESET} ${BOLD}Status:${RESET}      ${status_color}$status${RESET}$(printf ' %.0s' $(seq 1 $((47 - ${#status})))) ${BLUE}║${RESET}"
    echo -e "${BLUE}║${RESET}                                                              ${BLUE}║${RESET}"
    echo -e "${BLUE}║${RESET} ${BOLD}Items Processed:${RESET} ${WHITE}$items_processed${RESET}$(printf ' %.0s' $(seq 1 $((41 - ${#items_processed})))) ${BLUE}║${RESET}"
    echo -e "${BLUE}║${RESET} ${BOLD}Items Modified:${RESET}  ${WHITE}$items_modified${RESET}$(printf ' %.0s' $(seq 1 $((41 - ${#items_modified})))) ${BLUE}║${RESET}"
    echo -e "${BLUE}║${RESET} ${BOLD}Warnings:${RESET}      ${YELLOW}$warnings${RESET}$(printf ' %.0s' $(seq 1 $((47 - ${#warnings})))) ${BLUE}║${RESET}"
    echo -e "${BLUE}║${RESET} ${BOLD}Errors:${RESET}        ${RED}$errors${RESET}$(printf ' %.0s' $(seq 1 $((47 - ${#errors})))) ${BLUE}║${RESET}"
    echo -e "${BLUE}║${RESET}                                                              ${BLUE}║${RESET}"
    echo -e "${BLUE}║${RESET} ${BOLD}Next Steps:${RESET}                                                ${BLUE}║${RESET}"

    # Word wrap next steps to fit
    local next_step_lines=()
    local current_line=""
    local word=""
    
    for word in $next_steps; do
        if (( ${#current_line} + ${#word} + 1 <= 56 )); then
            if [[ -z "$current_line" ]]; then
                current_line="$word"
            else
                current_line="$current_line $word"
            fi
        else
            next_step_lines+=("$current_line")
            current_line="$word"
        fi
    done
    
    if [[ -n "$current_line" ]]; then
        next_step_lines+=("$current_line")
    fi
    
    for line in "${next_step_lines[@]}"; do
        echo -e "${BLUE}║${RESET}   ${CYAN}$line${RESET}$(printf ' %.0s' $(seq 1 $((55 - ${#line})))) ${BLUE}║${RESET}"
    done
    
    echo -e "${BLUE}║${RESET}                                                              ${BLUE}║${RESET}"
    echo -e "${BLUE}║${RESET} ${BOLD}Time Elapsed:${RESET} ${WHITE}$time_elapsed${RESET}$(printf ' %.0s' $(seq 1 $((43 - ${#time_elapsed})))) ${BLUE}║${RESET}"
    echo -e "${BLUE}╚════════════════════════════════════════════════════════════════════╝${RESET}"
}

Common Pitfalls to Avoid

    Inconsistent styling across script sections
    Clashing colors that reduce readability
    Over-animation that distracts from functionality
    Implementing visual elements that slow script execution
    Using colors without sufficient contrast for readability
    Relying on terminal features without fallbacks

Considerations for Various Scripting Scenarios
For Security Scripts

    Implement color-coded threat levels
    Design visual indicators for security status
    Create intuitive visualization of security posture
    Add visual emphasis to critical security findings
    Include timeline visualization for security events
    Implement visual confirmation for security actions

For System Maintenance Scripts

    Design progress visualization for system tasks
    Create visual disk usage representations
    Implement color-coded system health indicators
    Design visual comparison of before/after states
    Add real-time resource usage visualizations

For Data Processing Scripts

    Implement visual data flow representations
    Create progress indicators for batch operations
    Design summary visualizations of processed data
    Add visual markers for data transformation steps
    Include before/after data comparison visuals

For Network Scripts

    Design visual network topology representations
    Create color-coded connection status indicators
    Implement visual bandwidth utilization meters
    Add animated packet flow visualizations
    Include latency and response time visuals

For Backup/Restore Scripts

    Implement visual backup progress representation
    Create color-coded backup integrity indicators
    Design visual verification of backup completeness
    Add timeline visualization of backup history
    Include space utilization visualizations

Testing Expectations

Provide comprehensive testing covering:

    Visual element rendering consistency
    Performance impact of visual enhancements
    User experience flow and intuitiveness
    Error handling and recovery processes
    Edge cases and exceptional conditions

Ensure all visual elements enhance rather than detract from functionality, and that the script remains performant despite its beautiful presentation.

LOGICAL -
Comprehensive Bash Script Requirements
Best Practices

    Check Before Acting: Verify state (e.g., if a service is running or a file exists) before performing actions like stopping, deleting, or modifying
    Error Handling: Use robust error handling (set -e, set -u, trap for cleanup)
    Input Validation: Validate all input and parameters rigorously
    Secure Coding: Avoid hardcoding paths. Use environment variables or secure credential stores
    Modularity: Use functions for reusable, modular code
    Documentation: Add concise comments to explain key steps inside the script

Organization

    Logical Structure: Split the script into logical sections (Initialization, Functions, Main Logic, Cleanup)
    Visual Dividers: Separate sections with clear visual dividers (e.g., # ---- Section Title ----)
    Self-Documenting Code: Use meaningful variable and function names that explain their purpose

Visual Design & User Experience

    Color Scheme: Implement a dark background-optimized color palette using ANSI escape codes
    Aesthetic: Use pastel tones in a Jazz-inspired, cool, mature style for all text output
    Color Variables: Define color variables at the script beginning for consistent theming
    Auto-Detection: Detect terminal color support and fall back gracefully when unavailable
    Visual Hierarchy: Use colors to distinguish between warnings, errors, success messages, and general information
    Font Styling: Implement bold, italic, and underline formatting for emphasis where supported
    Borders and Panels: Create bordered sections for key information using Unicode box-drawing characters

Interactive Elements

    Progress Bars: Implement dynamic progress bars for long-running operations
    Spinners: Add elegant terminal spinners during wait times with custom-styled indicators
    Countdown Timers: Display countdown timers for operations with known durations
    Dynamic Updates: Use carriage returns to update status in-place rather than scrolling
    Typewriter Effects: Add typewriter-style text for important announcements or summaries
    Cursor Control: Hide/show cursor during animations for cleaner visuals
    Screen Clearing: Selectively clear screen sections while preserving history when appropriate
    Interactive Menus: Create stylish select menus for user choices
    Confirmations: Design elegant Y/N prompts with timeout defaults
    Animations: Implement simple ASCII/Unicode animations for transitions
    Sound Effects: Optional terminal bell for critical alerts (with flag to disable)

Efficiency

    Resource Conservation: Avoid unnecessary operations (e.g., don't stop a service if it's not running)
    Safety Measures: Use --dry-run or simulation options for destructive actions
    Progress Indicators: Implement pv or progress indicators for long-running tasks to provide real-time updates

Logging

    Verbosity Levels: Include verbose logging with configurable detail levels
    Timestamps: Add timestamps to all log entries for tracking and forensics
    Output Methods: Write logs to both stdout and file for later analysis
    Executive Summary: Generate an actionable log summary at script completion that provides:
        Critical Metrics: Only metrics that matter (e.g., "5 files deleted")
        Actionable Insights: Clear statements about outcomes and next steps
    Visual Logs: Style logs with the aesthetic theme while ensuring readability

Documentation

    Script Header: Include description, author, version, usage instructions
    Usage Examples: Show examples of running the script with common parameters
    Parameter Guide: Document all command-line options with explanations
    Visual Help: Create styled help screens and man-page-like formatted documentation

Enterprise Readiness

    Exit Codes: Return appropriate status codes (0 for success, non-zero for different failure types)
    Configurability: Support command-line flags to control behavior (e.g., -v for verbose, -q for quiet)
    Idempotency: Ensure running the script multiple times produces the same result
    Environment Adaptability: Detect and adjust to different environments automatically

Graceful Performance Degradation

    Feature Detection: Check for required tools for visual elements (e.g., ncurses, tput)
    Fallbacks: Provide simpler visual alternatives when advanced features aren't available
    No-Color Mode: Include a --no-color flag to disable all styling for logs/redirected output
    Non-Interactive Mode: Support a clean, non-interactive mode for scripted/automated usage
    Low-Resource Mode: Detect system constraints and reduce visual elements accordingly

BUG FREE -
Comprehensive Testing & Error-Proofing

Please deliver a fully tested, bug-free version of [script_name] that handles all possible execution scenarios:
Workflow Testing

    Single-run operations, multi-step sequences, looped operations
    All command-line flags and interactive modes
    Parallel execution and sequential workflows
    Initialization, main execution, and cleanup phases

Input Handling

    Valid inputs within expected ranges
    Invalid inputs: negative numbers, non-numeric strings, special characters
    Empty inputs or missing required parameters
    Excessively long inputs that might cause buffer overflows
    Piped inputs from other commands
    Unicode and non-ASCII character handling

Environment Compatibility

    Distribution variants: Debian, Ubuntu, CentOS, Fedora, RHEL
    Desktop environments: X11, Wayland, headless servers
    User contexts: root privileges, standard user, restricted user
    Interface types: GUI environments, terminal/TTY only
    Network status: online, offline, limited connectivity
    System state: fresh install, cluttered system, limited resources
    Shell variations: bash, zsh, sh, dash
    Terminal types: xterm, rxvt, konsole, Terminal.app, screen, tmux

Dependency Management

    Detect missing required tools and install them
    Handle outdated dependency versions gracefully
    Manage partial installations and conflicting packages
    Work with non-standard PATH configurations
    Handle sudo access restrictions and prompts
    Verify tool functionality post-installation
    Gracefully continue if optional tools are unavailable

Edge Case Handling

    Permission issues: no write/read access to needed directories
    Resource limitations: full disk, insufficient RAM, CPU constraints
    Network issues: timeouts, slow connections, DNS failures
    Terminal limitations: no color support, no clear command
    External tool crashes or unexpected behavior
    Killed or zombie processes
    Terminal size changes during execution

Interrupt Recovery

    Handle Ctrl+C (SIGINT) gracefully
    Manage SIGTERM and SIGKILL signals
    Account for session logout or disconnection
    Recover from power loss or system crash during execution
    Resume operations where possible after interruption

Implementation Requirements

The script must:
Install Dependencies Flawlessly

    Update package lists with retries and fallbacks
    Handle sudo permission issues (no tty, password prompts)
    Provide manual installation instructions if automation fails
    Verify tool functionality after installation
    Skip gracefully if optional dependencies can't be installed

Handle All Errors Comprehensively

    Catch and log all exceptions (file operations, commands, pipes)
    Provide detailed diagnostics for troubleshooting
    Present user-friendly recovery options (retry, skip, exit)
    Never hang indefinitely or exit silently
    Convert cryptic errors into actionable messages

Adapt Dynamically to the Environment

    Detect system configurations using multiple methods
    Adjust tool usage based on available commands
    Support both root and non-root user contexts correctly
    Determine correct home directories and config locations
    Select appropriate alternatives for environment-specific tools

Manage System Resources Effectively

    Create files and directories with explicit permissions
    Clean up temporary files even if execution is interrupted
    Implement proper locking to avoid race conditions
    Limit CPU and memory usage for resource-intensive operations
    Check available disk space before large file operations

Validate All Outputs Thoroughly

    Verify created files exist and contain expected content
    Confirm logs, notifications, and other outputs were generated
    Implement retry logic or fallbacks for failed operations
    Provide human-readable success/failure confirmation
    Check integrity of critical outputs

Recover Gracefully from Failures

    Preserve partial state when interrupted
    Support clean restart if re-executed
    Maintain idempotency to avoid duplicate operations
    Roll back changes if full completion isn't possible
    Save progress for long-running operations

Implement Comprehensive Logging

    Record all actions, inputs, errors, and system states
    Include environment variables and configuration in debug logs
    Support configurable verbosity levels
    Add timestamps to all entries
    Implement fallback logging if primary method fails

Enhance Visual Presentation

    Define a consistent color scheme for different message types
    Implement progress bars and spinners for long-running operations
    Create visually distinct sections for different script phases
    Use styled headers and footers for major operations
    Design an aesthetically pleasing executive summary display

Perform Self-Diagnostics

    Check prerequisites (bash version, required permissions)
    Warn about potential issues before they cause problems
    Suggest fixes for common configuration problems
    Verify script integrity and dependencies before execution
    Test critical permissions and access before main operations

Support Debugging and Troubleshooting

    Include a --debug flag for detailed tracing
    Implement verbose mode with step-by-step execution reports
    Provide a --dry-run option to simulate operations
    Log intermediate states and decision points
    Display environment information for troubleshooting

Visual Implementation Functions

Include utility functions for:

    Terminal width/height detection
    Color support detection
    Progress bar generation with custom styling
    Spinner animation with multiple style options
    Text styling (bold, italic, dim, etc.)
    Boxed/bordered text for important messages
    Centered text display
    Multi-column output formatting
    Terminal cursor positioning
    Typewriter text effect for important announcements
    Color theme definition and application

Executive Summary Format

At the end of execution, display a visually appealing summary like:

╔════════════════════════════════════════════╗
║             Executive Summary              ║
╠════════════════════════════════════════════╣
║ Task:      [script purpose]                ║
║ Status:    [success/failure/partial]       ║
║ Items Processed:   [count]                 ║
║ Items Modified:    [count]                 ║
║ Warnings:  [count]                         ║
║ Errors:    [count]                         ║
║                                            ║
║ Next Steps:                                ║
║   [actionable recommendation]              ║
║                                            ║
║ Time Elapsed: [duration]                   ║
╚════════════════════════════════════════════╝

Common Pitfalls to Avoid

    Assuming color support without checking terminal capabilities
    Creating flashy visuals that obscure important information
    Implementing animations that increase CPU usage significantly
    Using visual elements that break when terminal is resized
    Making script dependent on external tools for core functionality
    Failing to provide fallbacks for terminals without visual capabilities
    Using escape sequences that aren't portable across terminal types
    Creating progress indicators that don't accurately reflect actual progress

Interactive Element Implementation

For each interactive element, ensure:

    Keyboard shortcuts are displayed when relevant
    User can cancel operations with consistent key presses
    Elements respond appropriately to terminal resizing
    All interactive elements can be disabled via command flags
    Elements fall back gracefully in unsupported terminals
    Interactive prompts have sensible timeouts and defaults
    Help text is available for all interactive sections

Testing Expectations

Please provide a detailed testing checklist covering:

    Normal operation scenarios
    Common error cases and recovery
    Edge cases and exceptional conditions
    Performance under stress or resource limitations
    Security and permission boundary testing
    Visual element rendering across different terminal types
    Interaction with screen readers and accessibility tools

Preemptively fix all potential issues, including:

    Permission errors when switching between user contexts
    Tool compatibility across distributions and environments
    Silent failure modes that might hide problems
    Dependency installation challenges
    Output corruption or encoding issues
    Terminal compatibility issues with visual elements
    Performance degradation from excessive visual updates

If any feature might fail in certain environments, include a clear warning and fallback mechanism.
