import React, { useState } from 'react'
import { faqData } from '../../data/faq'

const FAQSection: React.FC = () => {
  const [openFAQ, setOpenFAQ] = useState<string | null>(null)

  const toggleFAQ = (id: string) => {
    setOpenFAQ(openFAQ === id ? null : id)
  }

  return (
    <section className="bg-white py-24">
      <div className="max-w-screen-xl mx-auto px-6 md:px-8">
        <div className="max-w-4xl mx-auto">
          <div className="text-center">
            <p className="text-xs text-gray-900 border border-gray-500 rounded-xl p-2 w-fit mx-auto mb-5">
              <span className="text-gray-800">FAQ's</span> ・ WHAT CLIENTS ASK US
            </p>
            <h2 className="text-3xl md:text-4xl font-bold tracking-tight leading-tight mt-2 mb-6">
              Frequently Asked Questions
            </h2>
            <p className="text-xl text-gray-900 leading-7 max-w-4xl mt-5 mx-auto pb-10">
              Answering your questions about roofing.
            </p>
          </div>
          
          <dl className="border-t border-gray-900/10 mt-10">
            {faqData.map((faq, index) => (
              <div 
                key={faq.id} 
                className={index === 0 ? 'pt-6' : 'border-t border-gray-900/10 mt-6 pt-6'}
              >
                <dt>
                  <button 
                    type="button" 
                    className="flex items-start justify-between w-full p-0 text-left text-gray-900 bg-transparent"
                    onClick={() => toggleFAQ(faq.id)}
                  >
                    <span className="block font-semibold leading-7">
                      {faq.question}
                    </span>
                    <span className="flex items-center h-7 ml-6">
                      <img 
                        src="https://c.animaapp.com/met7iikdASfhcY/assets/icon-12.svg" 
                        alt="Toggle" 
                        className={`w-6 h-6 transition-transform duration-200 ${
                          openFAQ === faq.id ? 'rotate-180' : ''
                        }`}
                      />
                    </span>
                  </button>
                </dt>
                {openFAQ === faq.id && (
                  <dd className="mt-2 pr-12">
                    <p 
                      className="text-gray-600 leading-7" 
                      dangerouslySetInnerHTML={{ __html: faq.answer }} 
                    />
                  </dd>
                )}
              </div>
            ))}
          </dl>
          
          <div className="text-center border-t border-gray-900/10 mt-8 pt-4">
            <p className="text-gray-600 mb-4">
              For expert advice on roof replacements in Florida, contact us
              today for a free inspection!
            </p>
            <a 
              href="/faqs" 
              className="inline-flex items-center text-lg font-semibold text-blue-600 leading-7 hover:text-blue-800 transition-colors"
            >
              View All FAQs
              <span className="block ml-2">→</span>
            </a>
          </div>
        </div>
      </div>
    </section>
  )
}

export default FAQSection
