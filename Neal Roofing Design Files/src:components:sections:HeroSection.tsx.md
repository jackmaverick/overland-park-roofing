import React, { useState } from 'react'
import { FormData } from '../../types'

const HeroSection: React.FC = () => {
  const [formData, setFormData] = useState<FormData>({
    service: '',
    address: '',
    name: '',
    email: '',
    phone: '',
    consent: false
  })

  const handleInputChange = (e: React.ChangeEvent<HTMLInputElement | HTMLSelectElement>) => {
    const { name, value, type } = e.target
    setFormData(prev => ({
      ...prev,
      [name]: type === 'checkbox' ? (e.target as HTMLInputElement).checked : value
    }))
  }

  const handleSubmit = (e: React.FormEvent<HTMLFormElement>) => {
    e.preventDefault()
    console.log('Form submitted:', formData)
  }

  return (
    <section className="relative bg-cover bg-center pt-10 pb-20" style={{backgroundImage: "url('https://nealrfg.com/images/core/roof.avif')"}}>
      <div className="absolute inset-0 bg-gray-900/90"></div>
      
      <div className="relative max-w-screen-xl mx-auto px-8">
        <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
          {/* Left Column - Content */}
          <div className="flex items-center">
            <div>
              {/* Trust Indicators */}
              <div className="flex items-center justify-between gap-10 mb-5">
                <div className="flex items-center gap-1">
                  <img src="https://c.animaapp.com/met7iikdASfhcY/assets/tree-left.webp" alt="Leaf" className="h-10" />
                  <p className="text-white text-xs md:text-sm leading-tight max-w-[100px] md:max-w-[130px]">
                    <span className="font-bold">4.9—STAR</span><br />
                    RATED BY 400+<br />
                    CUSTOMERS
                  </p>
                  <img src="https://c.animaapp.com/met7iikdASfhcY/assets/tree-right.webp" alt="Leaf" className="h-10" />
                </div>
                
                <div className="flex items-center gap-3">
                  <img src="https://c.animaapp.com/met7iikdASfhcY/assets/protection.svg" alt="Protection" className="h-10" />
                  <p className="text-white text-xs md:text-sm leading-tight">
                    <span className="font-bold">50-YEAR</span><br />
                    PRODUCT<br />
                    WARRANTIES
                  </p>
                </div>
              </div>
              
              {/* Main Heading */}
              <h1 className="text-4xl md:text-6xl font-bold text-white leading-tight mb-6">
                #1 Top-Rated Roofing Company<br />
                in <span className="text-violet-200">Florida</span>
              </h1>
              
              {/* Description */}
              <p className="text-gray-300 text-lg mb-8">
                With over 50 years in the roofing industry, our team is ready to
                answer your questions and address your concerns.{' '}
                <span className="font-bold">We know you will be thrilled with the finished product.</span>
              </p>
              
              {/* Service Tags */}
              <div className="flex flex-col md:flex-row gap-4">
                {['Roof Replacement', 'Roof Repair', 'Roofing Services'].map((service) => (
                  <div key={service} className="flex items-center gap-3 bg-gray-900/90 text-white text-sm px-4 py-3 rounded-full">
                    <img src="https://c.animaapp.com/met7iikdASfhcY/assets/icon-5.svg" alt="Check" className="w-4 h-4" />
                    {service}
                  </div>
                ))}
              </div>
            </div>
          </div>
          
          {/* Right Column - Form */}
          <div className="mt-16 md:mt-0">
            <div className="bg-gray-900/60 border border-gray-600 rounded-xl p-6 md:p-10 max-w-md md:max-w-full mx-auto">
              <div className="text-center mb-6">
                <p className="text-white text-lg mb-1">
                  Schedule your <span className="font-bold underline">FREE</span>
                </p>
                <p className="text-white text-xl font-bold">
                  Roof Inspection/Estimate Today!
                </p>
              </div>
              
              <form onSubmit={handleSubmit} className="space-y-4">
                {/* Service Selection */}
                <select 
                  name="service" 
                  value={formData.service}
                  onChange={handleInputChange}
                  className="w-full p-3 bg-violet-100 border border-gray-300 rounded-md text-base"
                >
                  <option value="">Choose Service*</option>
                  <option value="Roof Replacement">Roof Replacement</option>
                  <option value="Roof Repair">Roof Repair</option>
                  <option value="Commercial Project">Commercial Project</option>
                </select>
                
                {/* Form Fields */}
                {[
                  { name: 'address', type: 'text', placeholder: 'Enter Full Address*' },
                  { name: 'name', type: 'text', placeholder: 'Name*' },
                  { name: 'email', type: 'email', placeholder: 'Email' },
                  { name: 'phone', type: 'tel', placeholder: 'Phone Number*' }
                ].map((field) => (
                  <input 
                    key={field.name}
                    type={field.type}
                    name={field.name}
                    placeholder={field.placeholder}
                    value={formData[field.name as keyof FormData] as string}
                    onChange={handleInputChange}
                    className="w-full p-3 bg-violet-100 border border-gray-300 rounded-md text-base"
                  />
                ))}
                
                {/* Consent Checkbox */}
                <label className="flex gap-2 text-gray-500 text-xs leading-tight">
                  <input 
                    type="checkbox" 
                    name="consent" 
                    checked={formData.consent}
                    onChange={handleInputChange}
                    className="mt-1 w-4 h-4 text-blue-600 border border-gray-500 rounded"
                  />
                  <span>
                    I agree to receive messages from Neal Roofing and
                    Waterproofing regarding my inquiry/service request. End
                    users can opt out by replying STOP or request more
                    information by replying HELP. Message frequency varies.
                    Message and data rates may apply. You may review our{' '}
                    <a href="/privacy-policy" className="underline">Privacy Policy</a>{' '}
                    to learn how your data is used.
                  </span>
                </label>
                
                {/* Submit Button */}
                <button 
                  type="submit" 
                  className="w-full bg-blue-500 text-white font-medium px-4 py-3 rounded-md hover:bg-blue-600 transition-colors"
                >
                  Schedule FREE Estimate
                </button>
              </form>
              
              {/* Reviews Image */}
              <img 
                src="https://c.animaapp.com/met7iikdASfhcY/assets/reviews.webp" 
                alt="Reviews" 
                className="w-full mt-5"
              />
            </div>
          </div>
        </div>
      </div>
    </section>
  )
}

export default HeroSection
