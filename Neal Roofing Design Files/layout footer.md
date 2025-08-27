import React from 'react'

const Footer: React.FC = () => {
  const footerServices = [
    { id: 'residential-roofing', label: 'Residential Roofing', href: '/services/residential-roofing' },
    { id: 'commercial-roofing', label: 'Commercial Roofing', href: '/services/commercial-roofing' },
    { id: 'roof-replacement', label: 'Roof Replacement', href: '/services/roof-replacement' },
    { id: 'roof-repair', label: 'Roof Repair', href: '/services/roof-repair' },
    { id: 'waterproofing', label: 'Waterproofing', href: '/services/waterproofing' },
    { id: 'shingle-metal-tile', label: 'Shingle, Metal, & Tile', href: '/services/shingle-metal-tile' },
    { id: 'view-all-services', label: 'View All Services', href: '/services' }
  ]

  const footerLocations = [
    { id: 'boca-raton', label: 'Boca Raton, FL', href: '/locations/boca-raton-fl' },
    { id: 'delray-beach', label: 'Delray Beach, FL', href: '/locations/delray-beach-fl' },
    { id: 'jupiter', label: 'Jupiter, FL', href: '/locations/jupiter-fl' },
    { id: 'palm-beach-gardens', label: 'Palm Beach Gardens, FL', href: '/locations/palm-beach-gardens-fl' },
    { id: 'wellington', label: 'Wellington, FL', href: '/locations/wellington-fl' },
    { id: 'view-all-locations', label: 'View All Locations', href: '/locations' }
  ]

  const socialLinks = [
    { 
      id: 'google', 
      href: "https://www.google.com/maps/place/Neal+Roofing+&+Waterproofing/@26.7176036,-80.054108,17z/data=!3m2!4b1!5s0x88d8d65b3069f99f:0x1fba9f542738e0cd!4m6!3m5!1s0x88d8d702f460c98d:0xc46c2fadb9ed179c!8m2!3d26.7175988!4d-80.0515277!16s/g/11rgjbktyx?entry=ttu", 
      icon: "https://c.animaapp.com/met7iikdASfhcY/assets/google-my-business.svg", 
      alt: 'Google My Business Profile' 
    },
    { 
      id: 'instagram', 
      href: "https://www.instagram.com/neal_roofing/", 
      icon: "https://c.animaapp.com/met7iikdASfhcY/assets/instagram-svgrepo-com.svg", 
      alt: 'Instagram' 
    },
    { 
      id: 'youtube', 
      href: "https://www.youtube.com/channel/UCOVhYuF_CA2jeWDCXmpPo5A?app=desktopg", 
      icon: "https://c.animaapp.com/met7iikdASfhcY/assets/youtube-168-svgrepo-com.svg", 
      alt: 'Youtube' 
    },
    { 
      id: 'facebook', 
      href: "https://www.facebook.com/NealRoofing", 
      icon: "https://c.animaapp.com/met7iikdASfhcY/assets/facebook-svgrepo-com.svg", 
      alt: 'Facebook' 
    }
  ]

  return (
    <footer className="bg-white">
      <div className="max-w-screen-xl mx-auto pt-16 pb-8 px-6 md:px-8 border-t border-gray-200">
        <div className="grid grid-cols-1 md:grid-cols-2 gap-8 mt-10">
          {/* Left Section */}
          <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
            {/* Logo and License */}
            <div className="flex flex-col">
              <a href="/" className="block">
                <img 
                  src="https://c.animaapp.com/met7iikdASfhcY/assets/logo.webp" 
                  alt="Neal Roofing & Waterproofing" 
                  className="h-28"
                />
              </a>
              <p className="mt-4">
                Roofing Licenses:<br />
                <strong className="font-bold">CCC1332869 & CGC1537497</strong>
              </p>
            </div>
            
            {/* Services */}
            <div className="mt-10 md:mt-0">
              <h3 className="text-sm font-semibold text-gray-900">Services</h3>
              <ul role="list" className="mt-6 list-none pl-0">
                {footerServices.map((service, index) => (
                  <li key={service.id} className={index === 0 ? 'text-left' : 'text-left mt-4'}>
                    <a 
                      href={service.href} 
                      className="text-sm text-gray-600 hover:text-gray-900 transition-colors"
                    >
                      {service.label}
                    </a>
                  </li>
                ))}
              </ul>
            </div>
          </div>
          
          {/* Right Section */}
          <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
            {/* Locations */}
            <div>
              <h3 className="text-sm font-semibold text-gray-900">Locations</h3>
              <ul role="list" className="mt-6 list-none pl-0">
                {footerLocations.map((location, index) => (
                  <li key={location.id} className={index === 0 ? 'text-left' : 'text-left mt-4'}>
                    <a 
                      href={location.href} 
                      className="text-sm text-gray-600 hover:text-gray-900 transition-colors"
                    >
                      {location.label}
                    </a>
                  </li>
                ))}
              </ul>
            </div>
            
            {/* Map */}
            <div className="mt-10 md:mt-0">
              <iframe 
                src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3563.838573879886!2d-80.0541079873575!3d26.717603568348235!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x88d8d702f460c98d%253A0xc46c2fadb9ed179c!2sNeal%2520Roofing%2520%2526%2520Waterproofing!5e0!3m2!1sen!2sus!4v1709778464404!5m2!1sen!2sus" 
                title="Google Business Profile" 
                className="w-full h-[300px] rounded"
              />
            </div>
          </div>
        </div>
        
        {/* Reviews Section */}
        <div className="flex flex-col md:flex-row md:items-center md:justify-between border-t border-gray-900/10 mt-16 pt-8">
          <div className="flex items-center gap-4">
            <div className="flex items-center gap-4">
              <img src="https://c.animaapp.com/met7iikdASfhcY/assets/google.png" alt="Google Reviews" className="h-12" />
              <div className="flex gap-2">
                {[...Array(5)].map((_, i) => (
                  <img 
                    key={i} 
                    src="https://c.animaapp.com/met7iikdASfhcY/assets/star-icon.svg" 
                    alt="Star" 
                    className="w-5 h-5 mb-1"
                  />
                ))}
              </div>
            </div>
          </div>
          <div className="mt-5 md:mt-0"></div>
        </div>
        
        {/* Bottom Section */}
        <div className="flex flex-col md:flex-row md:items-center md:justify-between border-t border-gray-900/10 mt-8 pt-8">
          {/* Social Links */}
          <div className="flex order-2 md:order-2">
            {socialLinks.map((social, index) => (
              <a 
                key={social.id} 
                href={social.href} 
                className={`block text-blue-500 hover:text-gray-500 transition-colors ${index > 0 ? 'ml-6' : ''}`}
              >
                <img src={social.icon} alt={social.alt} className="w-8 h-8" />
              </a>
            ))}
          </div>
          
          {/* Copyright */}
          <div className="order-1 md:order-1">
            <p className="text-xs text-gray-700 leading-5 mt-8 md:mt-0">
              © <span>2025</span> Neal Roofing & Waterproofing. All rights reserved.
            </p>
            <a 
              href="/privacy-policy" 
              className="text-xs leading-4 underline mt-4 inline-block"
            >
              Privacy Policy
            </a>
          </div>
        </div>
      </div>
    </footer>
  )
}

export default Footer
