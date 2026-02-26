# SHIFT4 AI Chat Home Page - Figma Design Specification

## Overview
This document provides a complete specification for recreating the SHIFT4 AI Chat home page in Figma at:
https://www.figma.com/design/CZvVIsGF13NNT9nBY1CaX3/Intelligence-Inbox?node-id=691-846

## Design System

### Colors
```
Primary Background: #f5f5f5
Card Background: #ffffff
Sidebar Background: transparent
Text Primary: #1a1a1a
Text Secondary: #525252
Text Tertiary: #737373
Text Muted: #a3a3a3
Border: #e5e5e5
Border Hover: #d4d4d4
Blue Primary: #2563eb
Blue Light: #eff6ff
Blue Border: #bfdbfe
Red Background: #fee2e2
Red Text: #991b1b
Red Border: #fca5a5
Green Background: #d1fae5
Green Text: #065f46
Green Border: #6ee7b7
Info Background: #f0f4ff
Info Border: #c7d2fe
Info Text: #1e40af
Context Background: #f9fafb
Gray Button: #737373
```

### Typography
```
Font Family: Nunito Sans
Title: 28px / 600 / #1a1a1a
Subtitle: 15px / 400 / #737373
Insight Title: 17px / 600 / #1a1a1a
Insight Description: 14px / 400 / #525252
Insight Context: 13px / 400 / #737373
Badge: 11px / 600 / uppercase / 0.5px letter-spacing
Button: 13px / 500
Input: 14px / 400
```

### Spacing
```
App Container: 16px gap, 16px padding
Sidebar Width: 280px
Sidebar Padding: 20px 0
Card Border Radius: 12px
Button Border Radius: 6px
Badge Border Radius: 16px
Input Border Radius: 30px
Main Content Border Radius: 16px
```

## Layout Structure (1440px+ viewport)

```
┌─────────────────────────────────────────────────────────────┐
│  App Container (flex, gap: 16px, padding: 16px)             │
│                                                              │
│  ┌─────────────┐  ┌──────────────────────────────────────┐ │
│  │  Sidebar    │  │  Main Content                        │ │
│  │  280px      │  │  flex: 1                             │ │
│  │             │  │                                      │ │
│  │  Logo       │  │  ┌────────────────────────────────┐ │ │
│  │             │  │  │ Header (absolute, gradient)    │ │ │
│  │  Actions    │  │  │ - Restaurant Selector (left)   │ │ │
│  │  - New Chat │  │  │ - Actions (right)              │ │ │
│  │  - Search   │  │  └────────────────────────────────┘ │ │
│  │  - Support  │  │                                      │ │
│  │             │  │  Home Content (scroll area)          │ │
│  │  History    │  │  ┌────────────────────────────────┐ │ │
│  │  (scroll)   │  │  │ Greeting Section               │ │ │
│  │             │  │  │ - Title                        │ │ │
│  │             │  │  │ - Subtitle                     │ │ │
│  │             │  │  └────────────────────────────────┘ │ │
│  │             │  │                                      │ │
│  │             │  │  Intelligence Feed                   │ │
│  │             │  │  ┌────────────────────────────────┐ │ │
│  │             │  │  │ Insight Card 1 (Urgent)        │ │ │
│  │             │  │  └────────────────────────────────┘ │ │
│  │             │  │  ┌────────────────────────────────┐ │ │
│  │             │  │  │ AI Nudge                       │ │ │
│  │             │  │  └────────────────────────────────┘ │ │
│  │             │  │  Timestamp: "Today"                  │ │
│  │             │  │  ┌────────────────────────────────┐ │ │
│  │             │  │  │ Insight Card 2 (Action Needed) │ │ │
│  │             │  │  └────────────────────────────────┘ │ │
│  │             │  │  ┌────────────────────────────────┐ │ │
│  │             │  │  │ Insight Card 3 (Opportunity)   │ │ │
│  │             │  │  └────────────────────────────────┘ │ │
│  │             │  │  Timestamp: "Yesterday"              │ │
│  │             │  │  ┌────────────────────────────────┐ │ │
│  │             │  │  │ Insight Card 4 (Trending Up)   │ │ │
│  │             │  │  └────────────────────────────────┘ │ │
│  │             │  │                                      │ │
│  │             │  │  ┌────────────────────────────────┐ │ │
│  │             │  │  │ Input Area (absolute, gradient)│ │ │
│  │             │  │  │ - Add button                   │ │ │
│  │             │  │  │ - Input field                  │ │ │
│  │             │  │  │ - Send button                  │ │ │
│  │             │  │  └────────────────────────────────┘ │ │
│  └─────────────┘  └──────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

## Components

### 1. Sidebar Component
```
Width: 280px
Background: transparent
Padding: 20px 0
Border Radius: 16px
Layout: vertical

Children:
├─ Logo (padding: 0 20px 24px 20px)
│  └─ Image: Logo.png (height: 24px)
│
├─ Sidebar Actions (padding: 0 12px, margin-bottom: 20px)
│  ├─ Button: New Chat (icon: Edit-pen.png)
│  ├─ Button: Search Chat (icon: search)
│  └─ Button: Support (icon: support)
│
└─ Chat History (flex: 1, overflow-y: auto, padding: 0 12px)
   ├─ Title: "CHAT HISTORY"
   └─ Items (list of chat items)
```

### 2. Header Component
```
Position: absolute (top: 0, z-index: 10)
Padding: 16px 24px 60px 24px
Background: linear-gradient(to top, rgba(255,255,255,0) 0%, rgba(255,255,255,0.95) 40%, rgba(255,255,255,1) 70%)
Layout: horizontal, space-between

Left Side:
└─ Restaurant Selector (pill shape)
   Background: #fafafa
   Border Radius: 24px
   Padding: 8px 16px
   Children:
   ├─ Icon: location_on
   ├─ Name: "Peter's Grill Brooklyn"
   ├─ ID: "0021341010"
   └─ Icon: expand_more

Right Side:
└─ Actions
   ├─ Icon Button: notifications
   └─ Avatar: Ellipse.png (32px circle)
```

### 3. Greeting Section
```
Max Width: 800px
Margin Bottom: 32px

├─ Title: "Good afternoon, Demo User 👋"
│  Font: 28px / 600 / #1a1a1a
│  Margin Bottom: 8px
│
└─ Subtitle: "I've been analyzing your operations..."
   Font: 15px / 400 / #737373
   Strong text: #1a1a1a / 600
```

### 4. Insight Card Component (Reusable)
```
Background: #ffffff
Border: 1px solid #e5e5e5
Border Radius: 12px
Padding: 20px
Hover: border-color: #d4d4d4, box-shadow: 0 2px 8px rgba(0,0,0,0.05)

Structure:
├─ Header (margin-bottom: 16px)
│  ├─ Badge (left)
│  │  Variants:
│  │  - Urgent: bg: #fee2e2, text: #991b1b, border: #fca5a5, icon: error
│  │  - Action Needed: bg: #fee2e2, text: #991b1b, border: #fca5a5, icon: warning
│  │  - Opportunity: bg: #d1fae5, text: #065f46, border: #6ee7b7, icon: lightbulb
│  │  - Trending: bg: #dbeafe, text: #1e40af, border: #93c5fd, icon: trending_up
│  └─ Time (right, optional)
│
├─ Title (with info icon)
│  Font: 17px / 600 / #1a1a1a
│  Margin Bottom: 8px
│  └─ Info Icon (18px, #a3a3a3, with popover on hover)
│
├─ Time Badge (if at top level)
│  Font: 12px / #a3a3a3
│  Margin Top: 8px
│
├─ Description
│  Font: 14px / 400 / #525252
│  Line Height: 1.5
│  Margin Bottom: 12px
│
├─ Context (optional)
│  Background: #f9fafb
│  Padding: 8px 12px
│  Border Radius: 6px
│  Font: 13px / 400 / #737373
│  Margin Bottom: 12px
│
├─ Connection Badge (optional)
│  Background: #f5f5f5
│  Padding: 6px 12px
│  Border Radius: 6px
│  Font: 12px / #737373
│  Icon: link (14px, #a3a3a3)
│  Margin Bottom: 12px
│
└─ Actions Row (space-between)
   ├─ Left Actions (gap: 8px)
   │  ├─ Primary Button (bg: #2563eb, text: #ffffff)
   │  └─ Secondary Button (bg: #ffffff, border: #e5e5e5, text: #525252)
   │
   └─ Feedback Icons (gap: 8px)
      ├─ Thumb Up (icon: thumb_up_outlined)
      └─ Thumb Down (icon: thumb_down_outlined)
```

### 5. AI Nudge Component
```
Background: #f0f4ff
Border: 1px solid #c7d2fe
Border Radius: 12px
Padding: 16px

├─ Content
│  Font: 14px / 400 / #1e40af
│  Line Height: 1.5
│  Margin Bottom: 12px
│
└─ Actions (gap: 8px)
   ├─ Button: "Show me the gaps"
   └─ Button: "Already handled it"

   Style:
   Background: #ffffff
   Border: 1px solid #2563eb
   Color: #2563eb
   Padding: 6px 14px
   Border Radius: 6px
   Hover: bg: #eff6ff
```

### 6. Feed Timestamp
```
Text: "Today" / "Yesterday"
Font: 12px / #a3a3a3
Text Align: center
Margin: 8px 0
```

### 7. Input Area Component
```
Position: absolute (bottom: 0)
Padding: 60px 24px 24px
Background: linear-gradient(to bottom, rgba(255,255,255,0) 0%, rgba(255,255,255,0.95) 40%, rgba(255,255,255,1) 70%)

Container:
Max Width: 800px
Margin: 0 auto

Input Wrapper:
Background: #ffffff
Border: 1px solid #e5e5e5
Border Radius: 30px
Padding: 10px 16px
Gap: 12px
Focus: border-color: #2563eb, box-shadow: 0 0 0 3px rgba(37,99,235,0.1)

Children:
├─ Add Button (circle, icon: add)
│  Size: 24px
│  Color: #737373
│
├─ Input Field (flex: 1)
│  Font: 14px / 400
│  Placeholder: "Ask anything about your restaurant"
│  Color: #a3a3a3
│
└─ Send Button (circle)
   Size: 36px
   Background: #737373
   Icon: arrow_upward (20px, white)
   Hover: bg: #525252
```

### 8. Info Popover Component
```
Position: absolute (below parent)
Width: 400px
Background: #ffffff
Border: 1px solid #e5e5e5
Border Radius: 12px
Box Shadow: 0 4px 16px rgba(0,0,0,0.12)
Padding: 16px

Structure:
├─ Section
│  ├─ Strong (13px / 600 / #1a1a1a)
│  └─ Paragraph (13px / 400 / #525252, line-height: 1.5)
│
├─ Divider (1px / #f5f5f5)
│
├─ Section
│  ├─ Strong
│  └─ Paragraph
│
└─ Preference Link (12px / #737373, link: #2563eb / underlined)
```

## Content for Each Insight Card

### Insight 1: Weekend Sales Drop (Urgent)
```
Badge: Urgent (red, error icon)
Title: "Your Saturday sales dropped $2,847 this weekend"
Time: "2 hours ago"
Description: "I noticed something unusual — Saturday was down 18% compared to last week. Since Saturday is normally your strongest day (28% of weekly revenue), I wanted to flag this early."
Actions:
- Primary: "Walk me through what happened"
- Secondary: "Help me fix this"
Info Popover:
- "Why I'm bringing this up: If this continues, you're looking at $12K+ in lost revenue this month..."
- "I noticed: You typically review weekend performance Monday mornings..."
```

### AI Nudge: Staffing Schedule
```
Content: "💡 Quick question: I saw some gaps in this week's staffing schedule during your usual peak hours. Want me to pull up the details, or are you already on it?"
Actions:
- "Show me the gaps"
- "Already handled it"
```

### Insight 2: Terminal Support (Action Needed)
```
Connection Badge: "I think this is connected to your Saturday sales drop — this terminal was offline during your dinner rush"
Badge: Action Needed (red, warning icon)
Title: "I drafted a support case for terminal ST-2341"
Time: "4 hours ago"
Description: "This terminal went offline at 9:15 AM. Based on the last 12 times you've handled cases like this, I drafted a support ticket using the language that typically gets the fastest response."
Actions:
- Primary: "Submit the case"
- Secondary: "Let me review it first"
```

### Insight 3: Revenue Opportunity (Opportunity)
```
Badge: Opportunity (green, lightbulb icon)
Title: "I think you're leaving $1,440/month on the table"
Time: "Today"
Description: "I've been watching your Friday and Saturday dinner service. You're turning away customers during the 6-8pm rush because the kitchen can't keep up. Adding one flex cook during those hours could change that."
Actions:
- Primary: "Talk through this with me"
- Secondary: "Show me the details"
```

### Insight 4: Menu Success (Trending Up)
```
Badge: Trending Up (blue, trending_up icon)
Title: "Your menu changes are working — lunch is up 12%"
Time: "Yesterday"
Description: "I wanted to share some good news. Since you refreshed the menu last week, lunch has been climbing. Tuesday hit a new record, and the trend looks solid."
Actions:
- Primary: "Show me what's working"
- Secondary: "Compare to others"
```

## Icons Used
- Material Icons (Google)
- Material Icons Outlined (Google)
- Custom: Logo.png (SHIFT4 logo)
- Custom: Edit-pen.png (sidebar action)
- Custom: Ellipse.png (user avatar)

## Interactive States

### Button Hover
- Sidebar Button: bg: #f5f5f5
- Icon Button: bg: #f5f5f5
- Insight Action Primary: bg: #1d4ed8
- Insight Action Secondary: bg: #f9fafb, border: #d4d4d4
- Send Button: bg: #525252

### Card Hover
- Insight Card: border: #d4d4d4, shadow: 0 2px 8px rgba(0,0,0,0.05)

### Input Focus
- Input Wrapper: border: #2563eb, shadow: 0 0 0 3px rgba(37,99,235,0.1)

### Feedback Icons
- Default: outlined, #a3a3a3
- Hover: #525252
- Active Helpful: filled, #16a34a
- Active Unhelpful: filled, #dc2626

## Gradients

### Header Gradient
```
linear-gradient(
  to top,
  rgba(255,255,255,0) 0%,
  rgba(255,255,255,0.95) 40%,
  rgba(255,255,255,1) 70%
)
```

### Input Area Gradient
```
linear-gradient(
  to bottom,
  rgba(255,255,255,0) 0%,
  rgba(255,255,255,0.95) 40%,
  rgba(255,255,255,1) 70%
)
```

## Implementation Notes

1. The design uses a fixed 280px sidebar with flexible main content area
2. Header and input areas use absolute positioning with gradients for smooth scroll behavior
3. Home content area has padding-top: 120px and padding-bottom: 180px to accommodate fixed header/input
4. Max-width of 800px is applied to greeting and input containers for optimal reading width
5. All cards use consistent 12px border radius
6. Insight cards are clickable and navigate to conversation pages
7. Feedback icons toggle between outlined/filled states
8. Info icons show popovers on hover with contextual information
9. The design is responsive and adapts to different viewport sizes

## File References
- Logo.png: SHIFT4 logo
- Edit-pen.png: New chat icon
- Ellipse.png: User avatar (32x32px circle)

## Scrollbar Styling
```
Width: 8px
Track: transparent
Thumb: #d4d4d4
Thumb Hover: #a3a3a3
Border Radius: 4px
```
