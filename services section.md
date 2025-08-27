import React from 'react'
import { services } from '../../data/services'

const ServicesSection: React.FC = () => {
  return (
    <section className="bg-violet-100 py-24 md:pb-32">
      <div className="max-w-screen-xl mx-auto px-6 md:px-8">
        <div className="text-center">
          <p className="text-xs text-gray-900 border border-gray-500 rounded-xl p-2 w-fit mx-auto mb-5">
            <span className="text-gray-800">OUR SERVICES</span> ・ TYPES OF ROOFINGS
          </p>
          <h2 className="text-3xl md:text-4xl font-bold leading-tight mt-1">
            Premier Roofing Services for Homes & Businesses in Florida
          </h2>
          <p className="text-lg text-gray-900 leading-7 max-w-4xl mt-5 mx-auto">
            Whether you need roof repairs, replacement, or maintenance, Neal
            Roofing & Waterproofing has the expertise to handle it all. Our
            comprehensive roofing solutions are tailored to meet your needs and
            ensure your home is protected. Trust us to deliver top-quality
            service and lasting results.
          </p>
        </div>
        
        {/* Services Grid */}
        <div className="flex justify-center mt-12 md:mt-16">
          <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
            {services.map((service, index) => (
              <div 
                key={service.id} 
                className={`max-w-sm border border-blue-500 rounded-lg shadow-lg ${index > 0 ? 'mt-4 md:mt-0' : ''}`}
              >
                <a href={service.href}>
                  <img 
                    src={service.image} 
                    alt={service.imageAlt} 
                    className={service.imageClassName}
                  />
                </a>
                <div className="bg-white p-5 rounded-b-md">
                  <a href={service.href}>
                    <h5 className="text-2xl font-bold tracking-tight leading-8 mb-2">
                      {service.title}
                    </h5>
                  </a>
                  <p className="mb-5">
                    {service.description}
                  </p>
                  <a 
                    href={service.href} 
                    className="inline-flex items-center text-sm font-medium border px-4 py-2 rounded-lg hover:bg-gray-50 transition-colors"
                  >
                    Explore service →
                  </a>
                </div>
              </div>
            ))}
          </div>
        </div>
        
        {/* CTA Section */}
        <div className="flex flex-col items-center justify-center gap-5 mt-20">
          <a 
            href="#contact" 
            className="inline-flex items-center gap-2 bg-blue-500 text-white text-lg font-semibold px-12 py-4 rounded-md hover:bg-blue-600 transition-colors"
          >
            Get My Free Estimate
            <img src="https://c.animaapp.com/met7iikdASfhcY/assets/icon-3.svg" alt="Arrow" className="w-5 h-5" />
          </a>
          
          <div className="flex gap-5">
            <div className="flex items-center gap-2 mb-5">
              <img src="https://c.animaapp.com/met7iikdASfhcY/assets/tree-left-black.png" alt="Leaf" className="h-7" />
              <p className="text-gray-800 text-xs leading-tight">
                <span className="font-bold">4.9—STAR</span><br />
                RATED BY<br />
                400+ CUSTOMERS
              </p>
              <img src="https://c.animaapp.com/met7iikdASfhcY/assets/tree-right-black.png" alt="Leaf" className="h-7" />
            </div>
            
            <div className="flex items-center gap-2">
              <img src="https://c.animaapp.com/met7iikdASfhcY/assets/protection-black.svg" alt="Protection" className="h-5" />
              <p className="text-gray-800 text-xs leading-tight">
                <span className="font-bold">50-YEAR</span><br />
                PRODUCT<br />
                WARRANTIES
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>
  )
}

export default ServicesSection
