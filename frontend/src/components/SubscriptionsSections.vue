<template>
  <!-- Subscription Plans Section -->
  <section class="subscription-plans">
    <div class="container">
      <h2 class="section-title">اشتراكات النادي</h2>
      <p class="section-subtitle">اختر الباقة المناسبة لاحتياجاتك اللياقية</p>
      
      <div class="plans-grid">
        <div 
          v-for="(plan, index) in subscriptionPlans" 
          :key="index" 
          class="plan-card"
          :class="{ popular: plan.popular }"
        >
          <div class="plan-header">
            <h3>{{ plan.name }}</h3>
            <div class="price">
              <span class="amount">{{ plan.price }}</span>
              <span class="period">/ {{ plan.period }}</span>
            </div>
            <div v-if="plan.popular" class="popular-badge">الأكثر شعبية</div>
          </div>
          
          <div class="plan-features">
            <ul>
              <li v-for="(feature, featureIndex) in plan.features" :key="featureIndex">
                <i class="fa-solid fa-check"></i>
                {{ feature }}
              </li>
            </ul>
          </div>
          
          <div class="plan-footer">
            <button class="subscribe-btn" :class="{ popular: plan.popular }">
              اشترك الآن
            </button>
          </div>
        </div>
      </div>
      
      <div class="plans-note">
        <p><i class="fa-solid fa-circle-info"></i> جميع الباقات تشمل إمكانية تجميد الاشتراك لمدة تصل إلى 14 يوم في السنة</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "SubscriptionPlans",
  data() {
    return {
      subscriptionPlans: [
        {
          name: "اشتراك شهري",
          price: "199 ر.س",
          period: "شهر",
          popular: false,
          features: [
            "وصول غير محدود إلى الصالة الرياضية",
            "استخدام المعدات والأوزان الحرة",
            "دخول غرفة الساونا والبخار",
            "استشارة لياقة أولية مجانية",
            "تجميد الاشتراك لمدة 7 أيام"
          ]
        },
        {
          name: "اشتراك شهرين",
          price: "359 ر.س",
          period: "شهرين",
          popular: false,
          features: [
            "جميع مزايا الاشتراك الشهري",
            "خصم 10% على جلسات التدريب الشخصي",
            "دخول إلى حوض السباحة",
            "جلسة تدريب شخصي مجانية واحدة",
            "تجميد الاشتراك لمدة 10 أيام"
          ]
        },
        {
          name: "اشتراك 3 أشهر",
          price: "499 ر.س",
          period: "3 أشهر",
          popular: true,
          features: [
            "جميع مزايا اشتراك الشهرين",
            "دخول غير محدود إلى جميع فصول اللياقة",
            "تحليل تكوين الجسم كل شهر",
            "خصم 15% على المكملات الغذائية",
            "تجميد الاشتراك لمدة 14 يوم"
          ]
        },
        {
          name: "اشتراك 6 أشهر",
          price: "899 ر.س",
          period: "6 أشهر",
          popular: false,
          features: [
            "جميع مزايا اشتراك 3 أشهر",
            "جلستان تدريب شخصي مجانيتان",
            "دخول مجاني للضيف مرة كل أسبوعين",
            "خصم 20% على جميع الخدمات الإضافية",
            "تجميد الاشتراك لمدة 30 يوم"
          ]
        },
        {
          name: "اشتراك سنوي",
          price: "1599 ر.س",
          period: "سنة",
          popular: false,
          features: [
            "جميع مزايا اشتراك 6 أشهر",
            "4 جلسات تدريب شخصي مجانية",
            "دخول مجاني للضيف مرة كل أسبوع",
            "خصم 25% على جميع الخدمات الإضافية",
            "تجميد الاشتراك لمدة 60 يوم"
          ]
        },
        {
          name: "باقة العائلة",
          price: "2799 ر.س",
          period: "سنة",
          popular: false,
          features: [
            "اشتراك لشخصين بالغين وطفلين",
            "جميع مزايا الاشتراك السنوي",
            "أنشطة ترفيهية عائلية شهرية",
            "خصم 30% على أنشطة الأطفال",
            "تجميد الاشتراك لمدة 45 يوم لكل فرد"
          ]
        }
      ]
    };
  }
};
</script>

<style scoped>
.subscription-plans {
  /* margin: 50px; */
  padding: 100px;
  background-color: #eee;
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

.plans-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 2rem;
}

.plan-card {
  background: white;
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s, box-shadow 0.3s;
  position: relative;
}

.plan-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
}

.plan-card.popular {
  border: 2px solid #ff6600;
  transform: scale(1.05);
}

.plan-card.popular:hover {
  transform: scale(1.05) translateY(-10px);
}

.plan-header {
  padding: 1.5rem;
  background: linear-gradient(135deg, #333, #555);
  color: white;
  text-align: center;
  position: relative;
}

.plan-card.popular .plan-header {
  background: linear-gradient(135deg, #ff6600, #ff8533);
}

.plan-header h3 {
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
  background: #ff6600;
  color: white;
  padding: 0.3rem 1.5rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: bold;
}

.plan-features {
  padding: 1.5rem;
}

.plan-features ul {
  list-style: none;
  padding: 0;
}

.plan-features li {
  padding: 0.7rem 0;
  border-bottom: 1px solid #eee;
  display: flex;
  align-items: center;
}

.plan-features li:last-child {
  border-bottom: none;
}

.plan-features i {
  color: #28a745;
  margin-left: 0.5rem;
}

.plan-footer {
  padding: 1.5rem;
  text-align: center;
}

.subscribe-btn {
  background-color: #333;
  color: white;
  border: none;
  padding: 0.8rem 2rem;
  border-radius: 5px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s;
  width: 100%;
}

.subscribe-btn:hover {
  background-color: #555;
}

.subscribe-btn.popular {
  background-color: #ff6600;
}

.subscribe-btn.popular:hover {
  background-color: #e65c00;
}

.plans-note {
  text-align: center;
  background: white;
  padding: 1rem;
  border-radius: 10px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
  max-width: 800px;
  margin: 0 auto;
}

.plans-note i {
  color: #ff6600;
  margin-left: 0.5rem;
}

/* Responsive Design */
@media (max-width: 992px) {
  .plans-grid {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .plan-card.popular {
    transform: none;
  }
  
  .plan-card.popular:hover {
    transform: translateY(-10px);
  }
}

@media (max-width: 600px) {
  .plans-grid {
    grid-template-columns: 1fr;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .section-subtitle {
    font-size: 1rem;
  }
}

@media (max-width: 400px) {
  .plan-header {
    padding: 1rem;
  }
  
  .amount {
    font-size: 2rem;
  }
}
</style>