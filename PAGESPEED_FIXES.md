# PageSpeed Insights Accessibility Fixes

## Summary
This document outlines the specific fixes made to address PageSpeed Insights accessibility errors related to buttons lacking accessible names.

## Critical Issues Fixed

### 1. Carousel Navigation Buttons (Reviews Component)
**Issue**: 8 carousel buttons with classes `carousel-prev-inner` and `carousel-next-inner` lacked accessible names.

**Fix Applied**:
```html
<!-- Before -->
<button class="carousel-prev-inner w-10 h-10 rounded-full ...">
  <svg class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path>
  </svg>
</button>

<!-- After -->
<button 
  class="carousel-prev-inner w-10 h-10 rounded-full ..."
  aria-label="Previous review"
>
  <svg 
    class="w-5 h-5 text-white" 
    fill="none" 
    stroke="currentColor" 
    viewBox="0 0 24 24"
    aria-hidden="true"
  >
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path>
  </svg>
</button>
```

**Impact**: Fixes 8 PageSpeed Insights errors in the Reviews carousel section.

### 2. Social Media Icon Links (Footer)
**Issue**: 4 social media links containing only SVG icons lacked accessible names.

**Fix Applied**:
```html
<!-- Before -->
<a href="#" class="text-[#99B0BB] hover:text-[#F48C06] transition-colors duration-200">
  <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
    <!-- Twitter icon path -->
  </svg>
</a>

<!-- After -->
<a 
  href="#" 
  aria-label="Visit our Twitter profile"
  class="text-[#99B0BB] hover:text-[#F48C06] transition-colors duration-200"
>
  <svg 
    class="w-6 h-6" 
    fill="currentColor" 
    viewBox="0 0 24 24"
    aria-hidden="true"
  >
    <!-- Twitter icon path -->
  </svg>
</a>
```

**Social Links Updated**:
- Twitter: "Visit our Twitter profile"
- Facebook: "Visit our Facebook page"
- LinkedIn: "Visit our LinkedIn profile"
- Pinterest: "Visit our Pinterest profile"

**Impact**: Fixes 4 PageSpeed Insights errors in the Footer section.

## ARIA Attributes Used

### aria-label
- **Purpose**: Provides an accessible name for elements that don't have visible text
- **Used on**: Icon-only buttons and links
- **Example**: `aria-label="Previous review"`

### aria-hidden="true"
- **Purpose**: Hides decorative SVG icons from screen readers to prevent redundant announcements
- **Used on**: SVG elements inside buttons/links that have aria-labels
- **Example**: `<svg aria-hidden="true">...</svg>`

## Verification Steps

1. **Run PageSpeed Insights**:
   - Navigate to https://pagespeed.web.dev/
   - Enter your site URL
   - Check Accessibility section for remaining issues

2. **Use Lighthouse Audit**:
   - Open Chrome DevTools (F12)
   - Go to Lighthouse tab
   - Run Accessibility audit
   - Verify all buttons have accessible names

3. **Test with Screen Readers**:
   - NVDA (Windows): https://www.nvaccess.org/
   - JAWS (Windows): https://www.freedomscientific.com/
   - VoiceOver (macOS): Built-in, press Cmd+F5
   - TalkBack (Android): Built-in accessibility feature

4. **Keyboard Navigation**:
   - Tab through all interactive elements
   - Verify carousel buttons are keyboard accessible
   - Test social media links with keyboard

## Best Practices Applied

✅ **Descriptive Labels**: Labels describe the action, not the icon
- Good: "Previous review", "Visit our Twitter profile"
- Bad: "Left arrow", "Social media"

✅ **Consistent Naming**: Similar buttons use similar label patterns
- All carousel buttons: "Previous review" / "Next review"
- All social links: "Visit our [Platform] profile"

✅ **Semantic HTML**: Using proper button and link elements
- Buttons for interactive actions
- Links for navigation
- Proper ARIA attributes for state management

✅ **SVG Accessibility**: Decorative SVGs hidden from screen readers
- SVG icons marked with `aria-hidden="true"`
- Prevents redundant announcements

## Files Modified

1. `src/components/layout/Reviews.astro` - Carousel buttons (8 fixes)
2. `src/components/layout/Footer.astro` - Social media links (4 fixes)
3. `src/components/ui/Button.astro` - Added ariaLabel prop support
4. Multiple page and layout components - Added aria-labels to CTA buttons

## Expected Results

After these fixes, PageSpeed Insights should report:
- ✅ All buttons have accessible names
- ✅ All interactive elements are properly labeled
- ✅ Decorative elements are hidden from screen readers
- ✅ Improved accessibility score

## Additional Resources

- [WCAG 2.1 Button Name](https://www.w3.org/WAI/WCAG21/Understanding/name-role-value.html)
- [MDN: aria-label](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)
- [MDN: aria-hidden](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-hidden)
- [WebAIM: Screen Reader Testing](https://webaim.org/articles/screenreader_testing/)
