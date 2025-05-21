
# 🦁 Cologne Zoo Dashboard

A web application for zookeepers to monitor animals and their health data. It provides an overview of all animals in the zoo, including their species, gender, age, weight, and other relevant information.

---

## 📦 Tech Stack

- **Framework**: Nuxt.js v3.11.1 (Vue 3 + TypeScript)
- **Styling**: Tailwind CSS via `@nuxtjs/tailwindcss`
- **Package Manager**: pnpm
- **Testing**: Vitest with `happy-dom`
- **Mock Data**: `@faker-js/faker`
- **Linting**: ESLint with `@antfu/eslint-config`
- **Type Checking**: TypeScript with `vue-tsc`

---

## 📁 Project Structure

```plaintext
cologne-zoo-dashboard/
├── app.vue                          # Main application component
├── components/
│   └── TheAnimalTable.vue           # Table component for animal data
├── composables/
│   └── useAnimals.ts                # Animal data composable
├── server/
│   └── api/
│       └── animals.get.ts           # API endpoint for animal data
├── utils/
│   ├── useCalculateAgeInYears.ts    # Utility to calculate age
│   └── useCalculateAgeInYears.test.ts # Tests for age calculation
├── fakeData.ts                      # Mock animal data generation
├── types.ts                         # TypeScript type definitions
├── nuxt.config.ts                   # Nuxt configuration
├── eslint.config.js                 # ESLint configuration
├── tsconfig.json                    # TypeScript configuration
├── TASKS.md                         # Project task list
└── package.json                     # Project dependencies and scripts
```

---

## 🚀 Getting Started

### ✅ Prerequisites

- Node.js (v18+)
- pnpm

### 🔧 Installation

```shell
git clone (my-repo-with-the-code)
cd cologne-zoo-dashboard
pnpm install
```

---

## 🧪 Running the Application

### 🛠 Development Mode

```shell
pnpm run dev
```

The app will be available at [http://localhost:3000](http://localhost:3000)

### 📦 Production Build

```shell
pnpm run build
pnpm run start
```

---

## 🧪 Testing

```shell
pnpm run test
```

---

## 🎯 Linting

```shell
pnpm run lint
```

---

## 🧬 Code Overview

### 🐾 Data Model

```typescript
interface Animal {
  name: string;
  species: string;
  gender: 'male' | 'female';
  birthdate: Date;
  favouriteFruit: 'banana' | 'apple' | 'cherry';
  height: number;
  weight: number;
}
```

### 🔹 Key Components

- **TheAnimalTable.vue**: Sortable table displaying animal data (sorted by name).
- **useAnimals.ts**: Fetches data from the mock API.
- **animals.get.ts**: API endpoint returning animal data via Faker.
- **useCalculateAgeInYears.ts**: Utility to calculate age from birthdate.

---

## 🌟 Features

### 📊 Animal Overview Table

- Sortable by name
- Displays key information: species, name, gender, age, weight
- Responsive design with card view on mobile devices

### 🔍 Animal Details View

- Click on any animal to view complete details
- Modal interface shows all animal properties
- Maintains context of the full animal list

### 🍎 Food Calculation

- Calculates food requirements for the next calendar month
- Uses the zookeeper's formula:

  - Base: (height + weight) / 250
  - Age adjustments: half for >20 years, double for <2 years
  - Cherry lovers: +28kg for cherry as favorite fruit
  - Gender adjustment: +20% for males
  - Special case: 0kg for fish

- Provides both total food needed and per-animal breakdown

---

## 🛠️ Technical Notes

### 🔄 Server-Side Rendering

The application uses Nuxt.js with SSR. When working with browser APIs, ensure they're wrapped in client-side checks:

```javascript
// Correct way to use browser APIs
if (process.client) {
  // Browser-only code here
}
```

### 📅 Date Handling

Dates from the API may be serialized as strings. The `useCalculateAgeInYears` utility handles both Date objects and string dates:

```javascript
// Handles both Date objects and string dates
export default (birthdate: Date | string) => {
  const birthdateObj = birthdate instanceof Date ? birthdate : new Date(birthdate)
  // calculation logic...
}
```

### 🧮 Food Calculation Algorithm

The food calculation is implemented in the `calculateDailyFood` function, which follows the specified formula with all required adjustments.

---

## 🔮 Future Improvements

- ✅ Add authentication for zookeepers
- ✅ Replace mock data with real database
- ✅ Add more filtering and sorting options
- ✅ Implement feeding schedule planner
- ✅ Add health tracking and medical records
- ✅ Create reporting and analytics dashboard
- ✅ Implement notification system for feeding times
- ✅ Add image gallery for each animal

---

##  Feeding Schedule Planner

A planned feature for scheduling animal feeding tasks:

- Plan feeding days and fruits for each animal
- View tasks grouped by day for easy planning
- Calculate required food amounts automatically
- Mark tasks as completed
- Filter and search functionality

This feature will help zookeepers organize their daily feeding routines and ensure all animals receive proper nutrition.

---

## 📬 Support

For help or issues, contact:📧 **admin [at] zoo-cologne [dot] de**

---

## 💭 Developer Notes

During the recovery and enhancement of this project, several challenges were addressed:

1. **Server-Side Rendering Issues**: Fixed browser API usage in SSR context
2. **Date Formatting**: Improved date handling for better display and calculations
3. **Responsive Design**: Enhanced mobile experience with adaptive layouts
4. **Type Safety**: Ensured proper TypeScript typing throughout the application



---

> 📝 *This README was created as part of project recovery efforts.* **Last updated:** May 21, 2025
