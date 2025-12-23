# Awesome-Gallery-Slider

```
import React from 'react';
import { Swiper, SwiperSlide } from 'swiper/react';
import { EffectCoverflow, Navigation } from 'swiper/modules';
import { HiOutlineArrowNarrowLeft, HiOutlineArrowNarrowRight } from 'react-icons/hi';
```
// Import Swiper styles

```
import 'swiper/css';
import 'swiper/css/effect-coverflow';
import 'swiper/css/navigation';
```

```
const Portfolio = () => {
  const categories = ["Website Design", "Graphic Design", "Website Development", "Microsoft Word", "Powerpoint", "Autocad Design"];
  
  const images = [
    "https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&w=800&q=80",
    "https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=800&q=80",
    "https://images.unsplash.com/photo-1476514525535-07fb3b4ae5f1?auto=format&fit=crop&w=800&q=80",
    "https://images.unsplash.com/photo-1503220317375-aaad61436b1b?auto=format&fit=crop&w=800&q=80",
    "https://images.unsplash.com/photo-1519681393784-d120267933ba?auto=format&fit=crop&w=800&q=80",
  ];

  return (
    <section className="bg-white py-16 px-4 font-sans min-h-screen flex flex-col items-center justify-center">
      {/* Header Section */}
      <div className="text-center mb-10">
        <span className="text-[10px] tracking-[0.2em] uppercase font-bold text-red-500">Gallery</span>
        <h2 className="text-4xl font-bold text-slate-900 mt-2">Twoinsoft Student Work Quality</h2>
        <p className="text-gray-500 mt-3 max-w-md mx-auto leading-relaxed">
          We are committed to provide our students highly professional  training. Here are some example of our students work quality. See our students work sample and quality…
        </p>
      </div>

      {/* Filter Buttons */}
      <div className="flex flex-wrap justify-center gap-2 mb-12 max-w-4xl">
        {categories.map((city, index) => (
          <button
            key={index}
            className={`px-5 py-1.5 rounded-full border text-sm transition-all duration-300 ${
              index === 0 
                ? "bg-red-700 text-white " 
                : "bg-transparent text-slate-700 border-gray-300 hover:border-slate-900"
            }`}
          >
            {city}
          </button>
        ))}
        <button className="px-5 py-1.5 rounded-full border border-gray-300 text-sm font-medium flex items-center gap-2 hover:bg-gray-50">
          View More <HiOutlineArrowNarrowRight />
        </button>
      </div>

      {/* Swiper Gallery */}
      <div className="relative w-full max-w-6xl group">
        <Swiper
          effect={'coverflow'}
          grabCursor={true}
          centeredSlides={true}
          slidesPerView={'auto'}
          loop={true}
          coverflowEffect={{
            rotate: 0,
            stretch: 0,
            depth: 150,
            modifier: 2.5,
            slideShadows: false,
          }}
          navigation={{
            nextEl: '.button-next',
            prevEl: '.button-prev',
          }}
          modules={[EffectCoverflow, Navigation]}
          className="mySwiper !pb-12"
        >
          {images.map((src, index) => (
            <SwiperSlide key={index} className="!w-[300px] sm:!w-[400px]">
              <div className="relative h-[450px] rounded-3xl overflow-hidden shadow-2xl">
                <img 
                  src={src} 
                  alt={`Travel ${index}`} 
                  className="w-full h-full object-cover"
                />
              </div>
            </SwiperSlide>
          ))}
        </Swiper>

        {/* Navigation Buttons */}
        <div className="flex justify-center gap-4 mt-8">
          <button className="button-prev  text-red-500 w-12 h-12 rounded-full border border-gray-300 flex items-center justify-center hover:bg-red-700 hover:text-white transition-all cursor-pointer">
            <HiOutlineArrowNarrowLeft size={20} />
          </button>
          <button className="button-next text-red-500 w-12 h-12 rounded-full border border-gray-300 flex items-center justify-center hover:bg-red-700 hover:text-white transition-all cursor-pointer">
            <HiOutlineArrowNarrowRight size={20} />
          </button>
        </div>
      </div>
    </section>
  );

```
};

export default Portfolio;
