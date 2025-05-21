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

```
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

```bash
git clone [repository-url]
cd cologne-zoo-dashboard
pnpm install
```

---

## 🧪 Running the Application

### 🛠 Development Mode

```bash
pnpm run dev
```

The app will be available at [http://localhost:3000](http://localhost:3000)

### 📦 Production Build

```bash
pnpm run build
pnpm run start
```

---

## 🧪 Testing

```bash
pnpm run test
```


---



## 🎯 Linting

```bash
pnpm run lint
```

---

## 🧬 Code Overview

### 🐾 Data Model

```ts
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

- **TheAnimalTable.vue**: Sortable table displaying animal data (sorted by weight).
- **useAnimals.ts**: Fetches data from the mock API.
- **animals.get.ts**: API endpoint returning animal data via Faker.
- **useCalculateAgeInYears.ts**: Utility to calculate age from birthdate.

---



## 🔮 Future Improvements

- ✅ Add authentication
- ✅ Replace mock data with real backend
- ✅ Improve filtering and sorting
- ✅ Add responsive/mobile-friendly design
- ✅ Implement detailed animal views
- ✅ Validate all form inputs


---

## 📬 Support

For help or issues, contact:  
📧 **admin [at] zoo-cologne [dot] de**

---

> 📝 _This README was created as part of project recovery efforts._  
> **Last updated:** May 21, 2025
