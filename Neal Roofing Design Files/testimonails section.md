import React from 'react'
import { customerReviews } from '../../data/testimonials'

const TestimonialsSection: React.FC = () => {
  return (
    <section className="bg-white py-24">
      <div className="max-w-md md:max-w-screen-xl mx-auto px-6 md:px-8 text-center">
        <div>
          <p className="text-xs text-gray-900 border border-gray-500 rounded-xl p-2 w-fit mx-auto mb-5">
            <span className="text-gray-800">TESTIMONIALS</span> ・ WHAT CLIENTS SAY ABOUT US
          </p>
          <h2 className="text-3xl md:text-4xl font-bold tracking-tight leading-tight mt-2">
            See Why Florida Residents Choose Us for Roofing
          </h2>
          <p className="text-xl text-gray-900 leading-7 max-w-4xl mt-5 mx-auto pb-10">
            Hear from homeowners who've experienced our service and see why they
            say we're the top roofers.
          </p>
        </div>
        
        {/* Reviews Grid */}
        <div className="grid grid-cols-1 md:grid-cols-3 gap-4 mt-8">
          {customerReviews.map((review, index) => (
            <blockquote 
              key={review.id} 
              className="relative bg-gray-100 shadow-lg border border-blue-500 rounded-lg p-12 flex flex-col justify-between h-full"
            >
              <img 
                src="https://c.animaapp.com/met7iikdASfhcY/assets/google.png" 
                alt="Google icon" 
                className="absolute top-2 left-4 w-12 h-12 z-10"
              />
              
              <div>
                {/* Star Rating */}
                <div className={`flex justify-center gap-0.5 ${index === 2 ? 'gap-1' : 'text-yellow-400'}`}>
                  {[...Array(5)].map((_, i) => (
                    <img 
                      key={i} 
                      src="https://c.animaapp.com/met7iikdASfhcY/assets/star-icon.svg" 
                      alt="Star" 
                      className="w-5 h-5 mb-1"
                    />
                  ))}
                </div>
                
                <div className="mt-4">
                  <h3 className="text-xl md:text-2xl font-bold leading-7 md:leading-8">
                    {review.name}
                  </h3>
                  <p className="text-gray-900 mt-4">
                    {review.content}
                  </p>
                </div>
              </div>
            </blockquote>
          ))}
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

export default TestimonialsSection
