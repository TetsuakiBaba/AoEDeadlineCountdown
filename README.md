# AoE Deadline Clock

A deadline management tool based on AoE (Anywhere on Earth) timezone. It displays a countdown to the AoE deadline (23:59:59 UTC-12) for a specified date, along with the deadline time in the user's local timezone.

## Features

### 📱 User Features
- **Real-time Countdown**: Displays remaining time to the specified deadline in seconds
- **Local Time Display**: Automatically calculates and displays deadline time in user's timezone
- **Responsive Design**: Compatible from mobile devices to desktop
- **Traditional Typography**: Classic design using Times New Roman font

### ⚙️ Administrator Features
- **Deadline Setting**: Easy setup of new deadline dates
- **URL Generation**: Automatic generation of URLs containing the set deadline
- **Past Date Validation**: Warning display when past dates are selected
- **One-Click Copy**: Easy copying of generated URLs to clipboard
- **Visual Feedback**: Icon changes when copy operation is completed

## Usage

### Basic Viewing
1. Open index.html in a browser
2. By default, displays an AoE deadline 30 days from the current time
3. Countdown and local time are automatically updated

### Setting Custom Deadlines
1. Click "Create a New Deadline URL" to open the admin panel
2. Select the desired deadline date in the date selection field
3. Click "Copy URL" button to copy the URL
4. Share the copied URL with participants

### URL Parameters
Deadline dates can be specified as URL parameters:
```
index.html?deadline=2024-12-25
```

## Technical Specifications

### AoE Time Calculation
- AoE is based on the world's latest timezone (UTC-12)
- Counts down to 23:59:59 AoE time on the specified date
- Equivalent to 11:59:59 of the following day in UTC time

### Supported Browsers
- Chrome (recommended)
- Firefox
- Safari
- Edge

### Dependencies
- Bootstrap 5.3.3 (CDN)
- Bootstrap Icons 1.11.3 (CDN)

## File Structure

```
AoEDeadlineClock/
├── index.html          # Main application
├── README.md          # This file
└── LICENSE            # MIT License
```

## Design Features

- **Card-based Layout**: Clear separation of viewing and admin functions
- **Accordion UI**: Admin features are initially collapsed
- **Color-coded UI**: Admin panel visually distinguished with red accent
- **Rich Icons**: Intuitive UI using Bootstrap Icons

## Customization

### Changing Default Deadline
Edit the default value in the `getDeadlineFromURL()` function:
```javascript
// Default: AoE deadline 30 days from current time
const now = new Date();
const defaultDate = new Date(now.getTime() + 30 * 24 * 60 * 60 * 1000); // 30 days later
return new Date(Date.UTC(defaultDate.getFullYear(), defaultDate.getMonth(), defaultDate.getDate() + 1, 11, 59, 59));
```

### Style Customization
Fonts and sizes can be adjusted through the `.time` class and `.card-title` class in CSS.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Bug reports and feature suggestions are welcome. Pull requests are also appreciated.

---

**About AoE (Anywhere on Earth)**
AoE is a timezone concept widely used in academic conferences and international events, meaning "valid as long as it's still that day somewhere on Earth." Specifically, it's based on the UTC-12 timezone.
