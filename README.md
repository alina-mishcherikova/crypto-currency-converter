# Crypto Converter

A modern, interactive cryptocurrency converter built with Vue 3 and Vite.

## Overview

This project is a web application that allows users to convert between different cryptocurrencies in real-time. It features a clean, intuitive interface for selecting cryptocurrencies and viewing conversion results, along with the ability to save favorite currency pairs.

## Features

- **Real-time Conversion**: Convert between various cryptocurrencies using current exchange rates
- **Dual Selectors**: Choose source and target cryptocurrencies with easy-to-use selector components
- **Favorites**: Save your frequently used currency pair conversions for quick access
- **Error Handling**: Clear error messages when conversions fail
- **Responsive Design**: Clean and user-friendly interface built with Vue 3

## Tech Stack

- **Framework**: Vue 3 (v3.5.25)
- **Build Tool**: Vite (v7.3.1)
- **Crypto Library**: crypto-convert (v2.1.7)
- **Module System**: ES Modules

## Project Structure

```
📦 Crypto Converter
├── src/
│   ├── App.vue                 # Main application component
│   ├── main.js                 # Entry point
│   ├── style.css               # Global styles
│   ├── assets/
│   │   └── style.css           # Additional style assets
│   └── components/
│       ├── Input.vue           # Input amount component
│       ├── Selector.vue        # Cryptocurrency selector dropdown
│       ├── Favourite.vue       # Favorites list component
│       └── HelloWorld.vue      # Demo/example component
├── public/                     # Static assets
├── package.json                # Project dependencies
├── vite.config.js              # Vite configuration
└── index.html                  # HTML entry point
```

## Installation

1. Clone the repository
2. Install dependencies:

```bash
npm install
```

## Available Scripts

- **`npm run dev`** - Start the development server with hot module replacement
- **`npm run build`** - Build the project for production
- **`npm run preview`** - Preview the production build locally

## How to Use

1. Select a cryptocurrency to convert **from** using the first selector
2. Select a cryptocurrency to convert **to** using the second selector
3. Enter the amount you want to convert in the input field
4. View the conversion result
5. Click the favorite button to save this currency pair for quick access later
6. Access your saved conversions from the favorites list

## Components

### App.vue

The main component that orchestrates the entire application, managing state for:

- Conversion amounts and results
- Selected cryptocurrencies
- Error messages
- Favorite currency pairs

### Input.vue

Handles user input for the amount to be converted and triggers the conversion process.

### Selector.vue

A dropdown selector component for choosing cryptocurrencies (source and target).

### Favourite.vue

Displays saved favorite currency pair conversions, allowing users to quickly switch between them.

## Development

This project uses Vite as its build tool, which provides fast hot module replacement (HMR) during development. Start the development server and the browser will auto-refresh as you make changes to your components.

## License

This project is part of a Vue course training project.
