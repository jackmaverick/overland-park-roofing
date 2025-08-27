import React from 'react'

const AboutSection: React.FC = () => {
  return (
    <div className="bg-gray-100 py-16 overflow-hidden">
      <div className="max-w-screen-xl mx-auto px-6 md:px-8">
        <div className="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
          {/* Content Column */}
          <div className="relative z-10">
            <div className="text-gray-900 max-w-none">
              <p className="text-lg font-semibold text-blue-500 leading-7">About</p>
              <h2 className="text-3xl md:text-4xl font-bold tracking-tight leading-8 md:leading-10 mt-4">
                Neal Roofing & Waterproofing
              </h2>
              
              <div className="space-y-4 mt-4">
                <p>
                  As co-founders and childhood friends, Sam and Andrew have always
                  dreamed of creating a business that not only excels in its field
                  but also truly makes a difference in the lives of our customers.
                  Fast forward to today, and Neal Roofing is serving over 2000
                  customers per year, in the communities that we grew up in.
                </p>
                
                <p>
                  Our humble beginnings started with a shared vision, rooted in
                  our close bond as friends and family. We wanted to create a
                  company that we could be proud of, and that would reflect our
                  values of integrity, hard work, and commitment. We've always
                  believed that the strength of our company lies in the
                  relationships we've built, and that is why we have carefully
                  handpicked our team, inviting family and close friends to join
                  us on this incredible journey.
                </p>
                
                <p>
                  As we've grown, we've also made it our mission to break the mold
                  and challenge the status quo in the roofing industry. We've
                  welcomed top talent from various sectors, embracing a diverse
                  and progressive approach to our work. By harnessing the power of
                  technology, we're continually striving to enhance our services
                  and make a real impact in the world of roofing.
                </p>
                
                <p>
                  We recognize that your home is more than just a building; it's a
                  sanctuary, a place where memories are made and cherished. With
                  this in mind, we consider it an honor to be entrusted with your
                  roofing and waterproofing needs. Our commitment to you goes
                  beyond the completion of a project; we aim to create lasting
                  relationships and to be your go-to roofing partner for years to
                  come.
                </p>
                
                <p>
                  As we continue to grow and evolve, we promise never to lose
                  sight of our roots, our passion for our work, and our dedication
                  to you, our valued customers. We are grateful for the
                  opportunity to serve you, and we look forward to building a
                  brighter, safer, and more comfortable future for your home and
                  family.
                </p>
                
                <p>
                  Thank you for considering Neal Roofing And Waterproofing. We
                  can't wait to welcome you to our ever-growing family.
                </p>
              </div>
            </div>
          </div>
          
          {/* Image Column */}
          <div className="flex items-center justify-center h-auto md:h-[500px] rounded">
            <img 
              src="https://c.animaapp.com/met7iikdASfhcY/assets/truck.jpeg" 
              alt="Neal Roofing & Waterproofing truck" 
              className="w-full h-full object-cover rounded-md"
            />
          </div>
        </div>
        
        {/* CTA Section */}
        <div className="flex flex-col items-center justify-center gap-5 mt-8">
          <a 
            href="#contact" 
            className="inline-flex items-center gap-2 bg-blue-500 text-white text-lg font-semibold px-12 py-4 rounded-md hover:bg-blue-600 transition-colors mt-20"
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
    </div>
  )
}

export default AboutSection
