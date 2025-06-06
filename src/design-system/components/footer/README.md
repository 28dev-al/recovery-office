# Footer Components

Footer components provide a consistent, harmonious footer structure for the Recovery Office website. These components follow sacred geometry principles for spacing, proportions, and visual harmony, creating a balanced user experience.

## Components

### Footer

The main container component that provides the footer structure and layout.

```tsx
import { Footer } from '../design-system/components/footer';

<Footer
  variant="dark"
  withBotanical={true}
  botanicalType="flowerOfLife"
  botanicalPosition="topRight"
  withWaveBorder={true}
  withLogo={true}
  logo={<Logo />}
  copyrightText="Recovery Office. All rights reserved."
>
  {/* Footer content goes here */}
</Footer>
```

#### Footer Component Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | React.ReactNode | | Content to render in the footer |
| variant | 'primary' \| 'secondary' \| 'tertiary' \| 'dark' \| 'light' | 'dark' | Background/color scheme variant |
| withBotanical | boolean | false | Whether to include botanical decoration |
| botanicalType | 'oliveBranch' \| 'flowerOfLife' \| 'vesicaPiscis' \| 'fibonacciSpiral' \| 'oliveLeaf' \| 'smallFlourish' | 'oliveBranch' | Type of botanical element |
| botanicalPosition | BotanicalPosition | 'topRight' | Position of the botanical element |
| withWaveBorder | boolean | false | Whether to add a wave-shaped top border |
| waveBorderColor | string | | Optional color for the wave border |
| withLogo | boolean | false | Whether to include the company logo |
| logo | React.ReactNode | | Logo component to display |
| bottomContent | React.ReactNode | | Additional content for the bottom section |
| copyrightText | string | 'All rights reserved' | Copyright text to display |
| copyrightYear | number | current year | Year for the copyright notice |
| className | string | | Additional classes |
| style | React.CSSProperties | | Additional styles |

### FooterLinks

A component that displays a group of links in the footer.

```tsx
import { FooterLinks } from '../design-system/components/footer';

<FooterLinks
  title="Navigation"
  links={[
    { label: 'Home', href: '/' },
    { label: 'About', href: '/about' },
    { label: 'Services', href: '/services' }
  ]}
  withLinkDecoration={true}
/>
```

#### FooterLinks Component Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| title | string | | Title for the link group |
| links | FooterLink[] | | Array of links to display |
| description | string | | Optional description text above links |
| spacing | 'xs' \| 'sm' \| 'md' \| 'lg' | 'md' | Vertical spacing between links |
| linkIcon | React.ReactNode | | Optional icon before each link |
| withLinkDecoration | boolean | false | Whether to show subtle decoration |
| children | React.ReactNode | | Optional additional content |
| className | string | | Additional classes |
| style | React.CSSProperties | | Additional styles |

#### FooterLink Type

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| label | string | | Link label text |
| href | string | | URL for the link |
| openInNewTab | boolean | false | Whether the link opens in a new tab |

### FooterSocial

A component that displays social media links in the footer.

```tsx
import { FooterSocial } from '../design-system/components/footer';

<FooterSocial
  title="Connect with us"
  links={[
    {
      platform: 'facebook',
      href: 'https://facebook.com/recoveryoffice',
      label: 'Facebook',
      icon: <FacebookIcon />
    },
    // Additional social links...
  ]}
  circular={true}
/>
```

#### FooterSocial Component Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| title | string | | Title for the social links section |
| links | SocialLink[] | | Array of social media links |
| description | string | | Optional description text |
| direction | 'horizontal' \| 'vertical' | 'horizontal' | Layout direction for icons |
| iconSize | 'xs' \| 'sm' \| 'md' \| 'lg' \| 'xl' | 'md' | Size of social icons |
| circular | boolean | true | Whether to use circular backgrounds |
| animated | boolean | true | Whether to animate icons on hover |
| children | React.ReactNode | | Optional additional content |
| className | string | | Additional classes |
| style | React.CSSProperties | | Additional styles |

#### SocialLink Type

| Property | Type | Description |
|----------|------|-------------|
| platform | string | Platform name (e.g., 'facebook') |
| href | string | URL for the social profile |
| icon | React.ReactNode | Icon component to display |
| label | string | Alt/title text for the link |

### FooterNewsletter

A component that allows users to sign up for a newsletter in the footer.

```tsx
import { FooterNewsletter } from '../design-system/components/footer';

<FooterNewsletter
  title="Stay Connected"
  description="Subscribe to receive our updates."
  onSubmit={handleSubscribe}
  successMessage="Thank you for subscribing!"
/>
```

#### FooterNewsletter Component Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| title | string | 'Subscribe to our newsletter' | Title for the newsletter section |
| description | string | 'Stay updated with our latest news...' | Description text |
| placeholder | string | 'Your email address' | Placeholder for email input |
| buttonText | string | 'Subscribe' | Text for submit button |
| onSubmit | (email: string) => Promise<void> \| void | | Handler for form submission |
| successMessage | string | 'Thank you for subscribing!' | Success message after submission |
| showSuccessIndicator | boolean | true | Whether to show success indicator |
| children | React.ReactNode | | Optional additional content |
| className | string | | Additional classes |
| style | React.CSSProperties | | Additional styles |

## Sacred Geometry Principles

All footer components incorporate sacred geometry principles:

1. **Golden Ratio (PHI)**: Using PHI (1.618) and its inverse (0.618) for proportions:
   - FooterNewsletter form has a golden ratio proportion (PHI:1) between input and button
   - Title underlines extend to PHI_INVERSE (61.8%) of container width
   - Success message animations use PHI_INVERSE-based timing

2. **Fibonacci Sequence**: Using Fibonacci numbers for spacing and timing:
   - Vertical spacing between elements follows Fibonacci sequence values
   - Animation timings are derived from Fibonacci numbers
   - Success message uses FIBONACCI[10] * 100 ms for display duration

3. **Sacred Animation**: Natural motion patterns in the animations:
   - Transitions use cubic-bezier curves based on PHI_INVERSE (0.618, 0, 0.382, 1)
   - Hover effects scale elements by PHI_INVERSE * PHI for harmonious transitions

## Usage Example

Here's a complete example showing how to use all footer components together:

```tsx
import {
  Footer,
  FooterLinks,
  FooterSocial,
  FooterNewsletter
} from '../design-system/components/footer';

const FooterExample = () => {
  // Navigation links
  const navLinks = [
    { label: 'Home', href: '/' },
    { label: 'About', href: '/about' },
    { label: 'Services', href: '/services' }
  ];

  // Social links
  const socialLinks = [
    {
      platform: 'facebook',
      href: 'https://facebook.com/recoveryoffice',
      label: 'Facebook',
      icon: <FacebookIcon />
    },
    // Additional social links...
  ];

  // Handle newsletter submission
  const handleSubscribe = async (email) => {
    await submitToAPI(email);
  };

  return (
    <Footer
      variant="dark"
      withBotanical={true}
      botanicalType="flowerOfLife"
      copyrightText="Recovery Office. All rights reserved."
    >
      {/* Company description */}
      <div>
        <p>Recovery Office is dedicated to holistic healing through sacred geometry principles.</p>
        
        <FooterSocial
          title="Connect with us"
          links={socialLinks}
        />
      </div>

      {/* Navigation links */}
      <FooterLinks
        title="Navigation"
        links={navLinks}
        withLinkDecoration={true}
      />

      {/* Newsletter signup */}
      <FooterNewsletter
        title="Stay Connected"
        description="Subscribe for updates on new healing methodologies."
        onSubmit={handleSubscribe}
      />
    </Footer>
  );
};
```

## Accessibility Considerations

The footer components are designed with accessibility in mind:

- Proper semantic HTML structure throughout
- Appropriate ARIA attributes on interactive elements
- Color contrast compliance with WCAG guidelines
- Keyboard navigable links and form elements
- Screen reader friendly labeling
