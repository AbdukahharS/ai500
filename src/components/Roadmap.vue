<script setup lang="ts"></script>

<template>
  <section id="roadmap" class="roadmap">
    <div class="container">
      <!-- Problem Cards Section -->
      <div class="problem-cards-section">
        <h2 class="section-title">Почему мы можем решить эту задачу</h2>
        <p class="section-subtitle">
          Уникальное сочетание экспертизы, опыта и страсти к инновациям в
          агротехнологиях
        </p>

        <div class="cards-grid">
          <div class="card">
            <div class="icon">🌾</div>
            <h3>Понимание агроклимата и климата</h3>
            <p>
              Наша команда имеет глубокие знания в агрономии и специфике работы
              в засушливых регионах. Мы изучили потребности фермеров и понимаем
              их ежедневные вызовы.
            </p>
          </div>

          <div class="card">
            <div class="icon">📍</div>
            <h3>Опыт в ML и разработке</h3>
            <p>
              15+ лет суммарного опыта команды в machine learning, backend и
              frontend разработке. Мы создавали решения для крупных компаний и
              знаем, как масштабировать продукты.
            </p>
          </div>

          <div class="card">
            <div class="icon">👥</div>
            <h3>Проекты участников</h3>
            <p>
              Члены команды реализовали успешные проекты в agritech, IoT и AI с
              реальными результатами: системы мониторинга полей, платформы
              прогноза урожая.
            </p>
          </div>

          <div class="card">
            <div class="icon">💚</div>
            <h3>Мотивация и цель</h3>
            <p>
              Мы стремимся решать реальную проблему и сделать сельское хозяйство
              устойчивым и эффективным. Забота об экологии и помощь фермерам —
              наша миссия.
            </p>
          </div>
        </div>
      </div>

      <!-- AI500 Project Section -->
      <div class="project-intro">
        <h2 class="project-title">AI500 Project</h2>
        <p class="project-subtitle">
          Инновационное решение на основе искусственного интеллекта
        </p>
      </div>

      <!-- Roadmap Timeline -->
      <div class="timeline-section">
        <h3 class="timeline-title">Дорожная карта</h3>
        <div class="timeline">
          <div class="timeline-item completed">
            <div class="timeline-dot">✓</div>
            <div class="timeline-line"></div>
            <span class="timeline-label">Идея</span>
          </div>
          <div class="timeline-item completed">
            <div class="timeline-dot">✓</div>
            <div class="timeline-line"></div>
            <span class="timeline-label">Прототип</span>
          </div>
          <div class="timeline-item current">
            <div class="timeline-dot">✓</div>
            <div class="timeline-line inactive"></div>
            <span class="timeline-label">MVP</span>
            <span class="timeline-badge">Текущий этап</span>
          </div>
          <div class="timeline-item">
            <div class="timeline-dot inactive">✓</div>
            <span class="timeline-label">Запуск</span>
          </div>
        </div>
      </div>

      <!-- Tech Stack Section -->
      <div class="tech-section">
        <h3 class="tech-title">Как мы реализуем решение</h3>

        <div class="tech-cards">
          <!-- Technologies Card -->
          <div class="tech-card white-card">
            <div class="tech-header">
              <div class="tech-icon">💻</div>
              <h4>Технологии</h4>
            </div>

            <div class="tech-category">
              <div class="category-icon">⚛️</div>
              <div class="category-content">
                <h5>Frontend</h5>
                <div class="tags">
                  <span class="tag">React</span>
                  <span class="tag">TypeScript</span>
                  <span class="tag">Tailwind CSS</span>
                  <span class="tag">Next.js</span>
                </div>
              </div>
            </div>

            <div class="tech-category">
              <div class="category-icon">⚙️</div>
              <div class="category-content">
                <h5>Backend</h5>
                <div class="tags">
                  <span class="tag">Node.js</span>
                  <span class="tag">Express</span>
                  <span class="tag">FastAPI</span>
                  <span class="tag">REST API</span>
                </div>
              </div>
            </div>

            <div class="tech-category">
              <div class="category-icon">🤖</div>
              <div class="category-content">
                <h5>AI & ML</h5>
                <div class="tags">
                  <span class="tag">Python</span>
                  <span class="tag">TensorFlow</span>
                  <span class="tag">OpenAI GPT</span>
                  <span class="tag">LangChain</span>
                </div>
              </div>
            </div>

            <div class="tech-category">
              <div class="category-icon">💾</div>
              <div class="category-content">
                <h5>База данных</h5>
                <div class="tags">
                  <span class="tag">PostgreSQL</span>
                  <span class="tag">MongoDB</span>
                  <span class="tag">Redis</span>
                  <span class="tag">Vector DB</span>
                </div>
              </div>
            </div>

            <div class="tech-category">
              <div class="category-icon">🔌</div>
              <div class="category-content">
                <h5>API</h5>
                <div class="tags">
                  <span class="tag">GraphQL</span>
                  <span class="tag">WebSocket</span>
                  <span class="tag">OAuth 2.0</span>
                  <span class="tag">JWT</span>
                </div>
              </div>
            </div>
          </div>

          <!-- AI Card -->
          <div class="tech-card green-card">
            <div class="tech-header">
              <div class="tech-icon">🤖</div>
              <h4>Как работает AI</h4>
            </div>

            <div class="ai-feature">
              <div class="ai-icon">🧠</div>
              <div class="ai-content">
                <h5>Модели</h5>
                <p>GPT-4, Claude, Custom Fine-tuned Models</p>
              </div>
            </div>

            <div class="ai-feature">
              <div class="ai-icon">📊</div>
              <div class="ai-content">
                <h5>Данные</h5>
                <p>Обработка и визуализация больших объёмов данных</p>
              </div>
            </div>

            <div class="ai-feature">
              <div class="ai-icon">💡</div>
              <div class="ai-content">
                <h5>Рекомендации</h5>
                <p>Персонализированные рекомендации на основе ML</p>
              </div>
            </div>

            <div class="ai-process">
              <h5>Процесс работы AI:</h5>
              <ul>
                <li>1. Сбор данных</li>
                <li>2. Обучение моделей</li>
                <li>3. Генерация решений</li>
                <li>4. Непрерывное улучшение</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <!-- Footer -->
      <footer class="footer">
        <div class="footer-content">
          <div class="footer-left">
            <div class="footer-logo">
              <div class="logo-icon">🌱</div>
              <span>AI500 Project</span>
            </div>
            <p class="footer-description">
              Инновационное решение на основе искусственного интеллекта,
              созданное для ресурса AI500
            </p>
            <button class="footer-button">
              🚀 Посмотреть задачи для AI500
            </button>
          </div>

          <div class="footer-right">
            <h4>Контакты</h4>
            <div class="contact-links">
              <a href="mailto:info@ai500project.com" class="contact-link">
                <span>📧</span>
                info@ai500project.com
              </a>
              <a href="https://t.me/ai500project" class="contact-link">
                <span>✈️</span>
                @ai500project
              </a>
              <a href="https://github.com/ai500project" class="contact-link">
                <span>💻</span>
                github.com/ai500project
              </a>
            </div>
          </div>
        </div>

        <div class="footer-bottom">
          <p>© 2025 AI500 Project. Все права защищены.</p>
        </div>
      </footer>
    </div>
  </section>
</template>

<style scoped>
.roadmap {
  background: linear-gradient(170.24deg, #2a2a2a 43.28%, #000000 75.36%);
  color: #ffffff;
  overflow: hidden;
  z-index: 50;
  height: auto !important;
}

.container {
  overflow-y: auto;
  overflow-x: hidden;
  max-width: 100%;
  padding: 120px 80px 60px 80px;
}

/* Problem Cards Section */
.problem-cards-section {
  margin-bottom: 80px;
}

.section-title {
  font-family: 'Livvic', sans-serif;
  font-size: 48px;
  font-weight: 300;
  text-align: center;
  margin-bottom: 16px;
  color: #ffffff;
}

.section-subtitle {
  font-family: 'Livvic', sans-serif;
  font-size: 20px;
  font-weight: 300;
  text-align: center;
  color: #e0f540;
  margin-bottom: 48px;
}

.cards-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 32px;
  max-width: 1200px;
  margin: 0 auto;
}

.card {
  background: #FFFFFF1A;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  padding: 40px;
  transition: all 0.3s ease;
}

.card:hover {
  background: rgba(255, 255, 255, 0.15);
  transform: translateY(-4px);
}

.card .icon {
  font-size: 56px;
  margin-bottom: 24px;
}

.card h3 {
  font-family: 'Livvic', sans-serif;
  font-size: 28px;
  font-weight: 300;
  margin-bottom: 16px;
  color: #e0f540;
}

.card p {
  font-family: 'Livvic', sans-serif;
  font-size: 18px;
  font-weight: 300;
  line-height: 1.6;
  color: #ffffff;
}

/* Project Intro */
.project-intro {
  text-align: center;
  margin-bottom: 80px;
}

.project-title {
  font-family: 'Kalnia', sans-serif;
  font-size: 100px;
  font-weight: 400;
  margin-bottom: 20px;
  color: #e0f540;
  text-transform: uppercase;
}

.project-subtitle {
  font-family: 'Livvic', sans-serif;
  font-size: 24px;
  font-weight: 300;
  color: #ffffff;
}

/* Timeline Section */
.timeline-section {
  margin-bottom: 80px;
}

.timeline-title {
  font-family: 'Livvic', sans-serif;
  font-size: 40px;
  font-weight: 300;
  text-align: center;
  margin-bottom: 48px;
  color: #ffffff;
}

.timeline {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 0;
  max-width: 900px;
  margin: 0 auto;
  position: relative;
}

.timeline-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
}

.timeline-dot {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  background: #e0f540;
  border: 2px solid #898989;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 28px;
  color: #000000;
  z-index: 2;
  position: relative;
}

.timeline-dot.inactive {
  background: #898989;
  border-color: #898989;
  color: #ffffff;
}

.timeline-item.current .timeline-dot {
  background: #e0f540;
  box-shadow: 0 0 20px rgba(224, 245, 64, 0.5);
}

.timeline-line {
  position: absolute;
  left: 100%;
  top: 28px;
  width: 140px;
  height: 2px;
  background: #e0f540;
  z-index: 1;
}

.timeline-line.inactive {
  background: #898989;
}

.timeline-label {
  margin-top: 20px;
  font-family: 'Livvic', sans-serif;
  font-size: 20px;
  font-weight: 300;
  color: #ffffff;
}

.timeline-badge {
  margin-top: 12px;
  padding: 6px 16px;
  background: rgba(224, 245, 64, 0.2);
  border-radius: 16px;
  font-size: 14px;
  font-weight: 300;
  color: #e0f540;
}

/* Tech Section */
.tech-section {
  margin-bottom: 80px;
}

.tech-title {
  font-family: 'Livvic', sans-serif;
  font-size: 40px;
  font-weight: 300;
  text-align: center;
  margin-bottom: 48px;
  color: #ffffff;
}

.tech-cards {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  max-width: 1200px;
  margin: 0 auto;
}

.tech-card {
  border-radius: 20px;
  padding: 48px;
  border: 2px solid rgba(255, 255, 255, 0.1);
}

.white-card {
  background: #FFFFFF1A;
  backdrop-filter: blur(10px);
  color: #ffffff;
}

.green-card {
  background: linear-gradient(170.24deg, #e0f540 0%, #c5d936 100%);
  color: #000000;
  border-color: #e0f540;
}

.tech-header {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 36px;
}

.tech-icon {
  font-size: 42px;
}

.tech-header h4 {
  font-family: 'Livvic', sans-serif;
  font-size: 32px;
  font-weight: 300;
}

.tech-category {
  display: flex;
  gap: 20px;
  margin-bottom: 28px;
}

.category-icon {
  font-size: 28px;
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(224, 245, 64, 0.1);
  border-radius: 12px;
  flex-shrink: 0;
}

.category-content h5 {
  font-family: 'Livvic', sans-serif;
  font-size: 20px;
  font-weight: 300;
  margin-bottom: 12px;
  color: #e0f540;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.tag {
  padding: 8px 14px;
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 12px;
  font-size: 15px;
  font-family: 'Livvic', sans-serif;
  font-weight: 300;
}

/* AI Features */
.ai-feature {
  display: flex;
  gap: 20px;
  margin-bottom: 28px;
}

.ai-icon {
  font-size: 28px;
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(0, 0, 0, 0.15);
  border-radius: 12px;
  flex-shrink: 0;
}

.ai-content h5 {
  font-family: 'Livvic', sans-serif;
  font-size: 20px;
  font-weight: 300;
  margin-bottom: 8px;
}

.ai-content p {
  font-family: 'Livvic', sans-serif;
  font-size: 16px;
  font-weight: 300;
}

.ai-process {
  margin-top: 36px;
  padding-top: 28px;
  border-top: 2px solid rgba(0, 0, 0, 0.2);
}

.ai-process h5 {
  font-family: 'Livvic', sans-serif;
  font-size: 20px;
  font-weight: 300;
  margin-bottom: 20px;
}

.ai-process ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.ai-process li {
  font-family: 'Livvic', sans-serif;
  font-size: 16px;
  font-weight: 300;
  padding: 10px 0;
}

/* Footer */
.footer {
  margin-top: 100px;
  padding-top: 48px;
  border-top: 2px solid rgba(255, 255, 255, 0.1);
}

.footer-content {
  display: flex;
  justify-content: space-between;
  margin-bottom: 48px;
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 16px;
  font-family: 'Livvic', sans-serif;
  font-size: 28px;
  font-weight: 300;
  margin-bottom: 20px;
  color: #e0f540;
}

.logo-icon {
  font-size: 40px;
}

.footer-description {
  font-family: 'Livvic', sans-serif;
  font-size: 18px;
  font-weight: 300;
  color: rgba(255, 255, 255, 0.8);
  max-width: 450px;
  margin-bottom: 28px;
  line-height: 1.6;
}

.footer-button {
  padding: 14px 28px;
  background: #e0f540;
  color: #000000;
  border: 2px solid #898989;
  border-radius: 16px;
  font-family: 'Livvic', sans-serif;
  font-size: 18px;
  font-weight: 300;
  cursor: pointer;
  transition: all 0.3s ease;
}

.footer-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 16px rgba(224, 245, 64, 0.4);
}

.footer-right h4 {
  font-family: 'Livvic', sans-serif;
  font-size: 24px;
  font-weight: 300;
  margin-bottom: 20px;
  color: #e0f540;
}

.contact-links {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.contact-link {
  display: flex;
  align-items: center;
  gap: 16px;
  font-family: 'Livvic', sans-serif;
  font-size: 18px;
  font-weight: 300;
  color: rgba(255, 255, 255, 0.8);
  text-decoration: none;
  transition: all 0.3s ease;
}

.contact-link:hover {
  color: #e0f540;
}

.contact-link span {
  font-size: 24px;
}

.footer-bottom {
  text-align: center;
  padding-top: 32px;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.footer-bottom p {
  font-family: 'Livvic', sans-serif;
  font-size: 16px;
  font-weight: 300;
  color: rgba(255, 255, 255, 0.5);
}
</style>
