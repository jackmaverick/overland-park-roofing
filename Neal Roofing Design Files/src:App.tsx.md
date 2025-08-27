import React from 'react'
import Header from './components/layout/Header'
import HeroSection from './components/sections/HeroSection'
import AsSeenOnSection from './components/sections/AsSeenOnSection'
import TestimonialsVideoSection from './components/sections/TestimonialsVideoSection'
import StandardsSection from './components/sections/StandardsSection'
import ServicesSection from './components/sections/ServicesSection'
import TestimonialsSection from './components/sections/TestimonialsSection'
import AboutSection from './components/sections/AboutSection'
import InstagramSection from './components/sections/InstagramSection'
import ContactSection from './components/sections/ContactSection'
import FAQSection from './components/sections/FAQSection'
import Footer from './components/layout/Footer'

function App() {
  return (
    <div className="min-h-screen bg-white">
      <Header />
      <main>
        <HeroSection />
        <AsSeenOnSection />
        <TestimonialsVideoSection />
        <StandardsSection />
        <ServicesSection />
        <TestimonialsSection />
        <AboutSection />
        <InstagramSection />
        <ContactSection />
        <FAQSection />
      </main>
      <Footer />
    </div>
  )
}

export default App
