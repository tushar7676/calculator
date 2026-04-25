# DOM Calculator

A modern, fully-functional web calculator built with vanilla HTML, CSS, and JavaScript. Features a sleek dark theme, full keyboard support, and zero dependencies.

## ✨ Features

### Core Functionality
- **Basic Arithmetic**: Addition, subtraction, multiplication, division
- **Decimal Support**: Full floating-point precision with smart rounding
- **Percentage Calculations**: Quick percentage operations
- **Live Expression Display**: See your complete calculation history
- **Smart Error Handling**: Division by zero detection with user-friendly messages
- **Clear & Backspace**: AC (all clear) and ⌫ (delete last digit) actions

### ⌨️ Full Keyboard Support
| Action | Keys |
|--------|------|
| Numbers | `0–9` |
| Operators | `+` `-` `*` `/` |
| Calculate | `Enter` or `=` |
| Delete | `Backspace` |
| Clear | `Esc` or `C` |

### 🎨 Premium UI/UX
- **Dark Theme** with electric neon accents (#e8ff47)
- **Smooth Animations** & visual feedback on interactions
- **Interactive States**: Hover and active button effects
- **Dynamic Font Scaling**: Automatically adjusts for long numbers
- **Subtle Glow Effects** & depth shadows for modern look
- **Grid Texture Background** for visual depth
- **Responsive Design**: Perfect display on all screen sizes

### ♿ Accessibility
- **ARIA Labels** for all buttons and regions
- **Live Regions** for real-time screen reader updates
- **Keyboard Shortcut Hints** displayed in the interface
- **Semantic HTML** with proper role attributes
- **Screen Reader Compatible** for users with visual impairments

## 🏗️ Architecture

### Design Philosophy
- **No `eval()`** — Safe arithmetic using pure functions only
- **Immutable State** — Centralized, predictable state management
- **Floating-Point Safety** — Handles rounding errors (e.g., 0.1 + 0.2 = 0.3)
- **Event Delegation** — Efficient button click handling
- **Smart Keyboard Mapping** — Key-to-action conversion with visual feedback

### Code Structure
```
State Object
    ↓
Action Handlers (digit, operator, equals, etc.)
    ↓
Pure Functions (calculate, formatResult)
    ↓
updateDisplay() (DOM Sync)
    ↓
DOM Updates
```

## 🚀 Quick Start

1. **Open in Browser**: Simply open `index2.html` in any modern web browser
2. **Start Calculating**: Click buttons or use your keyboard
3. **No Installation Needed**: No build step, no dependencies, no setup required!

### Example Usage
```
Type or Click: 42 + 8 = 
Display Shows: 50

Keyboard: 5 * 6 Enter
Display Shows: 30
```

## 📋 Browser Support
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## 🔧 Technical Details

### Pure Functions
```javascript
calculate(a, operator, b)  // Safe binary operations
formatResult(num)          // Precision-safe formatting
```

### State Management
```javascript
state = {
  current,       // Currently displayed number
  expression,    // Full expression (e.g., "42 + 8 +")
  operator,      // Last operator pressed
  operand,       // Left operand before operator
  waitingForNext,// Flag after operator
  justEvaled,    // Flag after equals
  hasError       // Error state flag
}
```

### Keyboard Event Mapping
- Numeric keys → digit input
- Operator keys → operation selection
- Backspace → delete last character
- Escape/C → clear all
- Enter/= → calculate result

## 🎯 Key Features Explained

### Smart Operator Chaining
Pressing multiple operators in sequence automatically evaluates the previous operation:
```
5 + 3 - 2 = 6
(calculates 5+3=8, then 8-2=6)
```

### Floating-Point Precision
Handles JavaScript's floating-point quirks:
```
0.1 + 0.2 = 0.3 (not 0.30000000000000004)
```

### Visual Feedback
- **Result Flash**: Main display highlights in neon on equals
- **Keyboard Feedback**: Button highlights when keys are pressed
- **Error State**: Red text for error messages

## 📁 File Structure
```
task_2/
├── index2.html          # Single-file calculator (HTML + CSS + JS)
├── README.md           # This file
└── .git/               # Git repository
```

## 💡 Usage Tips

1. **Quick Clear**: Press `Esc` or `C` anytime to start fresh
2. **Backspace Correction**: Use `Backspace` to fix the last digit
3. **Keyboard Speed**: Keyboard input is faster than clicking
4. **Long Calculations**: Results display with dynamic font sizing
5. **Operator Swap**: Change operator before entering next number

## 🐛 Error Handling
- **Division by Zero**: Shows "Can't ÷ by 0"
- **Invalid Input**: Automatically prevents invalid states
- **Precision Limits**: Caps display at 15 characters for readability

## 🎨 Design Tokens (CSS Variables)
```css
--bg:          #0d0d0f;        /* Deep black background */
--accent:      #e8ff47;        /* Electric chartreuse */
--text-primary:#f0f0f0;        /* Light text */
--radius:      16px;           /* Border radius */
```

All colors and spacing are customizable via CSS variables in `:root`.

## 📝 Code Quality
- **Strict Mode**: Uses `"use strict"` for safer code
- **Clear Comments**: Well-documented with section headers
- **No Global Pollution**: Functions scoped with const/let
- **Event Delegation**: Single event listener on grid
- **Accessibility-First**: ARIA attributes on all interactive elements

## 🔐 Security
- No use of `eval()` or `innerHTML`
- Safe arithmetic with explicit function calls
- Input validation on all user interactions
- XSS-safe DOM operations

## 🎓 Learning Resources

This calculator is an excellent example of:
- **Vanilla JavaScript DOM manipulation**
- **Event handling & keyboard input**
- **State management patterns**
- **CSS custom properties (design tokens)**
- **Accessible UI design**
- **Pure function architecture**

## 📄 License
Open source - feel free to use, modify, and distribute

## 👨‍💻 Author
Created as a demonstration of modern vanilla web development practices

---

**Try it now**: Open `index2.html` in your browser and start calculating! 🧮
