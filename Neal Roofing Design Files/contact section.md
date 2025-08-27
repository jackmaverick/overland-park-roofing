import React, { useState } from 'react'
import { contactInfo } from '../../data/contact'
import { ContactFormData } from '../../types'

const ContactSection: React.FC = () => {
  const [formData, setFormData] = useState<ContactFormData>({
    'first-name': '',
    'last-name': '',
    email: '',
    phone: '',
    message: ''
  })

  const handleInputChange = (e: React.ChangeEvent<HTMLInputElement | HTMLTextAreaElement>) => {
    const { name, value } = e.target
    setFormData(prev => ({
      ...prev,
      [name]: value
    }))
  }

  const handleSubmit = (e: React.FormEvent<HTMLFormElement>) => {
    e.preventDefault()
    console.log('Contact form submitted:', formData)
  }

  const formFields = [
    { name: 'first-name', label: 'First name', type: 'text', colSpan: 1 },
    { name: 'last-name', label: 'Last name', type: 'text', colSpan: 1 },
    { name: 'email', label: 'Email', type: 'email', colSpan: 1 },
    { name: 'phone', label: 'Phone', type: 'tel', colSpan: 1 },
    { name: 'message', label: 'Message', type: 'textarea', colSpan: 2 }
  ]

  return (
    <section id="contact" className="border-t border-gray-200 rounded-md">
      <div className="max-w-screen-xl mx-auto px-6 md:px-8 py-16 md:py-24">
        <div className="relative shadow-2xl rounded-md">
          <div className="grid grid-cols-1 md:grid-cols-3">
            {/* Contact Info Column */}
            <div className="relative bg-blue-500 px-6 py-10 md:p-12 rounded-md overflow-hidden">
              {/* Background Patterns */}
              <div className="absolute inset-0 block md:hidden">
                <img src="https://c.animaapp.com/met7iikdASfhcY/assets/icon-9.svg" alt="Pattern" className="absolute inset-0 w-full h-full" />
              </div>
              <div className="absolute right-0 inset-y-0 w-6/12 hidden">
                <img src="https://c.animaapp.com/met7iikdASfhcY/assets/icon-10.svg" alt="Pattern" className="absolute inset-0 w-full h-full" />
              </div>
              <div className="absolute right-0 inset-y-0 w-6/12 hidden md:block">
                <img src="https://c.animaapp.com/met7iikdASfhcY/assets/icon-11.svg" alt="Pattern" className="absolute inset-0 w-full h-full" />
              </div>
              
              <h3 className="text-lg font-medium text-white leading-7">
                Contact information
              </h3>
              <p className="text-indigo-50 max-w-screen-md mt-6">
                Thank you for considering us for roofing needs. We will get back
                to you during normal business hours.
              </p>
              
              <dl className="mt-8">
                {contactInfo.map((item) => (
                  <dd key={item.id} className={item.className}>
                    <img src={item.icon} alt={item.iconAlt} className="w-5 h-5" />
                    <a href={item.href} className="block">
                      {item.text}
                    </a>
                  </dd>
                ))}
              </dl>
            </div>
            
            {/* Form Column */}
            <div className="col-span-2 px-6 py-10 md:p-12">
              <h3 className="text-lg font-medium text-gray-900 leading-7">
                Send us a message
              </h3>
              
              <form onSubmit={handleSubmit} className="grid grid-cols-1 md:grid-cols-2 gap-6 md:gap-8 mt-6">
                {formFields.map((field) => (
                  <div 
                    key={field.name} 
                    className={field.colSpan === 2 ? 'col-span-1 md:col-span-2' : ''}
                  >
                    {field.type === 'textarea' ? (
                      <>
                        <div className="flex justify-between">
                          <label className="block text-sm font-medium text-gray-900 leading-5">
                            {field.label}
                          </label>
                          <span className="block text-sm text-gray-500 leading-5">
                            Max. 500 characters
                          </span>
                        </div>
                        <div className="mt-1">
                          <textarea 
                            name={field.name} 
                            className="block w-full px-4 py-3 text-gray-900 border-gray-300 rounded-md shadow-sm resize-y"
                            rows={4}
                            value={formData[field.name as keyof ContactFormData]}
                            onChange={handleInputChange}
                          />
                        </div>
                      </>
                    ) : (
                      <>
                        <label className="block text-sm font-medium text-gray-900 leading-5">
                          {field.label}
                        </label>
                        <div className="mt-1">
                          <input 
                            type={field.type} 
                            name={field.name} 
                            className="block w-full px-4 py-3 text-gray-900 border border-gray-300 rounded-md shadow-sm"
                            value={formData[field.name as keyof ContactFormData]}
                            onChange={handleInputChange}
                          />
                        </div>
                      </>
                    )}
                  </div>
                ))}
                
                <div className="col-span-1 md:col-span-2 flex flex-col justify-end">
                  <button 
                    type="submit" 
                    className="flex items-center justify-center w-full md:w-auto bg-blue-500 text-white font-medium px-6 py-3 rounded-md border border-transparent shadow-sm hover:bg-blue-600 transition-colors mt-2"
                  >
                    Submit
                  </button>
                  <span className="block text-xs text-gray-500 leading-4 text-center mt-6">
                    By pressing 'Submit' you are explicitly agreeing to our{' '}
                    <a href="/terms-conditions" className="underline">terms and conditions</a>{' '}
                    and{' '}
                    <a href="/privacy-policy" className="underline">privacy policy</a>, and
                    consenting to receive text messages. To unsubscribe, text
                    STOP to (561) 473-0192.
                  </span>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>
  )
}

export default ContactSection
