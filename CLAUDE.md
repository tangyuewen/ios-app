# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a high-fidelity prototype for a voice-based accounting application built with HTML, Tailwind CSS, and FontAwesome. The prototype demonstrates a streamlined "voice-to-accounting" workflow with zero-confirmation input, designed for iOS (iPhone 15 Pro dimensions).

## Core Design Philosophy

**Zero-Confirmation Interaction**: The app's key differentiator is immediate voice recognition and auto-accounting without manual confirmation steps. When users speak their expenses, the system parses and records them automatically.

**Error Resilience**: Supports fuzzy voice commands (e.g., "coffee cost over 20 yuan", "cab about 35 yuan") with auto-completion and correction capabilities.

**Minimal Friction**: Core workflow requires ≤2 steps, using lightweight toast notifications instead of intrusive dialogs.

## Architecture

### File Structure
- `prototype/` - Contains all high-fidelity UI prototypes
  - `index.html` - Main entry point displaying all screens side-by-side using iframes
  - `home.html` - Voice记账首页 (Core feature with giant microphone button)
  - `records.html` - 账单列表页 (Bill management with filtering)
  - `stats.html` - 数据统计页 (Data visualization with Chart.js)
  - `profile.html` - 个人中心页 (User settings and achievements)
  - `edit.html` - 快速编辑页 (Quick edit for corrections)
  - `settings.html` - 设置页 (System preferences)

### UI Framework
- **Styling**: Tailwind CSS with violet-bloom theme (purple-based color palette)
- **Icons**: FontAwesome 6.4.0 via CDN
- **Charts**: Chart.js for statistics visualization
- **Design System**: CSS custom properties for consistent theming

## Theme System

The prototype uses the violet-bloom color scheme:
- Primary: `#9333EA` (violet-500)
- Gradients: `#8B5CF6` to `#9333EA`
- Backgrounds: `#F8FAFC` (slate-50)
- All colors defined in CSS `:root` variables for easy customization

## Key UI Patterns

### Phone Container
- Dimensions: 393×852px (iPhone 15 Pro)
- Border radius: 30px
- Shadow: Multi-layer for realistic depth

### Tab Bar
- Height: 83px (includes safe area)
- Active state: violet-500 color
- Icons + text labels

### Interaction Feedback
- Microphone button: Pulse animation and scale effects
- Toast notifications: Lightweight feedback for user actions
- Slide-up animations: For list items and modals

## Development Notes

### Working with Iframes
The main `index.html` uses iframes to display all prototypes simultaneously. When modifying individual screens:
1. Changes in prototype files automatically reflect in the overview
2. Tab switching works across all iframes
3. Event handling must be managed within each iframe's context

### Responsive Considerations
All prototypes are designed for iPhone 15 Pro dimensions but include:
- Viewport meta tags preventing zoom
- Custom scrollbar styling
- Touch-friendly tap targets (minimum 44px height)

### Theme Migration
Originally designed with mint green theme (#4ADE80), now migrated to violet-bloom theme. All color references use CSS variables for easy theme switching.