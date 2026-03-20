# Accessibility Updates - Aria-Labels for Screen Readers

## Overview
All buttons throughout the BuildPro website have been reviewed and updated with proper `aria-label` attributes to improve accessibility for screen reader users.

## Changes Made

### 1. Button Component (`src/components/ui/Button.astro`)
- Added `ariaLabel` prop to the Button component interface
- Button component now accepts and renders `aria-label` attribute
- This allows all Button instances to have descriptive labels for screen readers

### 2. Hero Section (`src/components/layout/Hero.astro`)
- **Main CTA Button**: "View our portfolio of completed projects"
- **Slideshow Navigation Dots**: 
  - Slide 1: "Go to slide 1"
  - Slide 2: "Go to slide 2"
  - Slide 3: "Go to slide 3"
  - Slide 4: "Go to slide 4"
  - Slide 5: "Go to slide 5"

### 3. Hero2 Section (`src/components/layout/Hero2.astro`)
- **Back Link**: "Navigate back to [backText]" (dynamic based on context)
- **Form Submit Button**: "Submit the form to get your free quote"

### 4. CTA Section (`src/components/layout/CTASection.astro`)
- **Consultation Form Submit**: "Submit consultation request form"

### 5. FAQ Section (`src/components/layout/FAQ.astro`)
- **FAQ Item 1**: "Toggle answer: How long does a typical project take?"
- **FAQ Item 2**: "Toggle answer: Do you offer warranties on your work?"
- **FAQ Item 3**: "Toggle answer: What payment methods do you accept?"
- **FAQ Item 4**: "Toggle answer: Are your contractors licensed and insured?"
- **FAQ Item 5**: "Toggle answer: How do I get a free estimate?"

### 6. Navbar (`src/components/layout/Navbar.astro`)
- **Desktop CTA Button**: "Navigate to contact page to get a quote"
- **Mobile CTA Button**: "Navigate to contact page to get a quote"

### 7. Call Banner (`src/components/layout/CallBanner.astro`)
- **CTA Button**: "Navigate to contact page to get your quote"

### 8. Contact Form (`src/components/layout/ContactForm.astro`)
- **Form Submit Button**: "Submit contact form to request a free consultation"

### 9. Footer (`src/components/layout/Footer.astro`)
- **Get in Touch Button**: "Navigate to contact page to get in touch"

### 10. Our Work Page (`src/pages/our-work.astro`)
- **View All HVAC Templates**: "View all HVAC website templates"
- **View All Plumbing Templates**: "View all plumbing website templates"

## Best Practices Implemented

1. **Descriptive Labels**: Each aria-label clearly describes the button's action or purpose
2. **Context-Aware**: Labels include context (e.g., "Toggle answer:" for FAQ items)
3. **Action-Oriented**: Labels use action verbs (View, Navigate, Submit, Toggle)
4. **Consistency**: Similar buttons have similar label patterns
5. **Screen Reader Friendly**: Labels are concise but informative

## Testing Recommendations

1. Test with screen readers (NVDA, JAWS, VoiceOver)
2. Verify that aria-labels are announced correctly
3. Ensure labels don't duplicate visible text unnecessarily
4. Test keyboard navigation with Tab key
5. Verify focus indicators are visible

## Future Considerations

- Monitor user feedback from screen reader users
- Consider adding aria-describedby for complex interactive elements
- Ensure all form inputs have associated labels
- Test with various assistive technologies
