<template>
  <!-- Diet Programs Section -->
  <section class="diet-programs">
    <div class="container">
      <h2 class="section-title">برامج التغذية</h2>
      <p class="section-subtitle">اختر البرنامج الغذائي المناسب لأهدافك</p>
      
      <div class="programs-grid">
        <div 
          v-for="(program, index) in dietPrograms" 
          :key="index" 
          class="program-card"
          :class="{ popular: program.popular }"
        >
          <div class="program-header">
            <h3>{{ program.name }}</h3>
            <div class="price">
              <span class="amount">{{ program.price }}</span>
              <span class="period">/ {{ program.period }}</span>
            </div>
            <div v-if="program.popular" class="popular-badge">الأكثر طلباً</div>
          </div>
          
          <div class="program-features">
            <ul>
              <li v-for="(feature, featureIndex) in program.features" :key="featureIndex">
                <i class="fa-solid fa-check"></i>
                {{ feature }}
              </li>
            </ul>
          </div>
          
          <div class="program-footer">
            <button class="subscribe-btn" :class="{ popular: program.popular }">
              ابدأ البرنامج
            </button>
          </div>
        </div>
      </div>
      
      <div class="programs-note">
        <p><i class="fa-solid fa-circle-info"></i> جميع البرامج تشمل متابعة أسبوعية مع أخصائي التغذية</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "DietProgramsSection",
  data() {
    return {
      dietPrograms: [
        {
          name: "برنامج التغذية الأساسي",
          price: "299 ر.س",
          period: "شهر",
          popular: false,
          features: [
            "خطة غذائية أسبوعية مخصصة",
            "متابعة أسبوعية مع أخصائي التغذية",
            "دليل القياسات والحصص الغذائية",
            "قائمة تسوق أسبوعية",
            "دعم عبر الواتساب"
          ]
        },
        {
          name: "برنامج خسارة الوزن",
          price: "499 ر.س",
          period: "شهر",
          popular: true,
          features: [
            "جميع مزايا البرنامج الأساسي",
            "خطة حرق دهون مكثفة",
            "متابعة يومية للسعرات الحرارية",
            "تحليل تكوين الجسم أسبوعياً",
            "وصفات صحية منخفضة السعرات"
          ]
        },
        {
          name: "برنامج كتلة عضلية",
          price: "599 ر.س",
          period: "شهر",
          popular: false,
          features: [
            "خطة غذائية لبناء العضلات",
            "برنامج مكملات غذائية مخصص",
            "متابعة زيادة الكتلة العضلية",
            "وصفات عالية البروتين",
            "نظام توقيت الوجبات"
          ]
        },
        {
          name: "برنامج الرياضيين",
          price: "799 ر.س",
          period: "شهر",
          popular: false,
          features: [
            "تغذية مخصصة لنوع الرياضة",
            "برنامج ما قبل وبعد التمرين",
            "إدارة الطاقة والأداء",
            "مكملات غذائية متقدمة",
            "تحليل أداء رياضي"
          ]
        },
        {
          name: "برنامج اللياقة المتكامل",
          price: "999 ر.س",
          period: "شهرين",
          popular: false,
          features: [
            "برنامج تغذية + تدريب شخصي",
            "3 جلسات تدريب شخصي أسبوعياً",
            "متابعة شاملة 24/7",
            "تحديث أسبوعي للبرنامج",
            "تحليل فيديو للأداء"
          ]
        },
        {
          name: "الباقة العائلية",
          price: "1799 ر.س",
          period: "شهرين",
          popular: false,
          features: [
            "برامج تغذية لـ 4 أفراد",
            "خطط وجبات عائلية متكاملة",
            "نصائح تغذية للأطفال",
            "وصفات صحية للعائلة",
            "خصم 20% على التجديد"
          ]
        }
      ]
    };
  }
};
</script>

<style scoped>
.diet-programs {
  padding: 5rem 0;
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
}

.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 1rem;
  color: #333;
}

.section-subtitle {
  text-align: center;
  font-size: 1.2rem;
  margin-bottom: 3rem;
  color: #666;
}

.programs-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 2rem;
}

.program-card {
  background: white;
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s, box-shadow 0.3s;
  position: relative;
  border: 1px solid #e9ecef;
}

.program-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
}

.program-card.popular {
  border: 2px solid #28a745;
  transform: scale(1.05);
}

.program-card.popular:hover {
  transform: scale(1.05) translateY(-10px);
}

.program-header {
  padding: 1.5rem;
  background: linear-gradient(135deg, #2c3e50, #3498db);
  color: white;
  text-align: center;
  position: relative;
}

.program-card.popular .program-header {
  background: linear-gradient(135deg, #28a745, #34ce57);
}

.program-header h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

.price {
  display: flex;
  justify-content: center;
  align-items: baseline;
}

.amount {
  font-size: 2.5rem;
  font-weight: bold;
}

.period {
  font-size: 1rem;
  margin-right: 0.5rem;
}

.popular-badge {
  position: absolute;
  top: -10px;
  left: 50%;
  transform: translateX(-50%);
  background: #28a745;
  color: white;
  padding: 0.3rem 1.5rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: bold;
}

.program-features {
  padding: 1.5rem;
}

.program-features ul {
  list-style: none;
  padding: 0;
}

.program-features li {
  padding: 0.7rem 0;
  border-bottom: 1px solid #eee;
  display: flex;
  align-items: center;
}

.program-features li:last-child {
  border-bottom: none;
}

.program-features i {
  color: #28a745;
  margin-left: 0.5rem;
}

.program-footer {
  padding: 1.5rem;
  text-align: center;
}

.subscribe-btn {
  background: linear-gradient(135deg, #2c3e50, #3498db);
  color: white;
  border: none;
  padding: 0.8rem 2rem;
  border-radius: 5px;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s;
  width: 100%;
  font-weight: bold;
}

.subscribe-btn:hover {
  background: linear-gradient(135deg, #3498db, #2c3e50);
  transform: translateY(-2px);
}

.subscribe-btn.popular {
  background: linear-gradient(135deg, #28a745, #34ce57);
}

.subscribe-btn.popular:hover {
  background: linear-gradient(135deg, #34ce57, #28a745);
}

.programs-note {
  text-align: center;
  background: white;
  padding: 1rem;
  border-radius: 10px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
  max-width: 800px;
  margin: 0 auto;
  border-right: 4px solid #28a745;
}

.programs-note i {
  color: #28a745;
  margin-left: 0.5rem;
}

/* Program Type Badges */
.program-type {
  position: absolute;
  top: 15px;
  left: 15px;
  background: rgba(255, 255, 255, 0.2);
  padding: 0.3rem 0.8rem;
  border-radius: 15px;
  font-size: 0.8rem;
  backdrop-filter: blur(10px);
}

/* Responsive Design */
@media (max-width: 992px) {
  .programs-grid {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .program-card.popular {
    transform: none;
  }
  
  .program-card.popular:hover {
    transform: translateY(-10px);
  }
}

@media (max-width: 600px) {
  .programs-grid {
    grid-template-columns: 1fr;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .section-subtitle {
    font-size: 1rem;
  }
  
  .diet-programs {
    padding: 3rem 0;
  }
}

@media (max-width: 400px) {
  .program-header {
    padding: 1rem;
  }
  
  .amount {
    font-size: 2rem;
  }
  
  .program-features {
    padding: 1rem;
  }
  
  .program-features li {
    font-size: 0.9rem;
  }
}
</style>