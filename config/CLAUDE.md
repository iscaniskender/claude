# Claude Desktop Skill Envanteri

Bu dosya, `Downloads/AllSkills.zip` içinde bulunan ve Claude Desktop'ta kullanılan skill setinin bir referansıdır. Claude Code, bu proje dışında çalışırken kullanıcının hangi iş akışlarına alışkın olduğunu bilmek için bu listeye bakabilir. Skill dosyalarının kendisi bu makinede `~/.claude/skills/` altında kurulu DEĞİL — bunlar Desktop tarafında kullanılan tanımlar, sadece referans amaçlı listelenmiştir.

## Giriş / Yönlendirme

- **using-superpowers** — Herhangi bir konuşmaya başlarken kullanılır; skill'lerin nasıl bulunup çağrılacağını belirler, herhangi bir yanıttan (açıklayıcı sorular dahil) önce skill çağrımını zorunlu kılar.
- **using-agent-skills** — Agent skill'lerini keşfeder ve çağırır; hangi skill'in mevcut göreve uyduğunu belirleyen meta-skill.
- **context-engineering** — Yeni bir oturuma başlarken, agent çıktı kalitesi düştüğünde veya görevler arası geçişte context/rules dosyalarını optimize eder.
- **brainstorming** — Herhangi bir yaratıcı çalışmadan (özellik oluşturma, bileşen ekleme, davranış değiştirme) önce kullanıcı niyetini, gereksinimleri ve tasarımı keşfeder.
- **interview-me** — Belirsiz isteklerde ("X yap" ama kime/niçin belirtilmemiş) kullanıcının gerçekte ne istediğini tek tek sorularla ~%95 güvene ulaşana kadar çıkarır.
- **idea-refine** — Ham fikirleri, ıraksak ve yakınsak düşünmeyle net ve uygulanabilir kavramlara dönüştürür; varsayımları plana geçmeden stres testine tabi tutar.
- **doubt-driven-development** — Önemli her kararı, karar kesinleşmeden önce taze bağlamlı, adversarial bir incelemeye tabi tutar (üretim/güvenlik/geri döndürülemez işlemler gibi yüksek riskli durumlarda).
- **karpathy-guidelines** — LLM'lerin yaygın kodlama hatalarını azaltmak için davranış kuralları: aşırı karmaşıklaştırmama, cerrahi değişiklikler, varsayımları açığa çıkarma, doğrulanabilir başarı kriterleri tanımlama.

## Planlama

- **spec-driven-development** — Kod yazmadan önce spec oluşturur; yeni proje/özellik/önemli değişiklik başlarken veya gereksinimler net değilken kullanılır.
- **planning-and-task-breakdown** — Spec veya net gereksinimler varken işi sıralı, uygulanabilir görevlere böler.
- **writing-plans** — Çok adımlı bir görev için spec/gereksinim varken, koda dokunmadan önce plan yazar.
- **executing-plans** — Yazılı bir uygulama planını, inceleme kontrol noktalarıyla ayrı bir oturumda yürütür.
- **incremental-implementation** — Birden fazla dosyayı etkileyen her özellik/değişikliği artımlı olarak teslim eder; büyük bir kod bloğu tek seferde yazılacaksa devreye girer.

## Uygulama

- **test-driven-development** (2 kopya, aynı içerik) — Herhangi bir mantık uygularken, hata düzeltirken veya davranış değiştirirken testlerle geliştirmeyi yönetir.
- **source-driven-development** — Her uygulama kararını resmi dokümantasyona dayandırır; framework/kütüphane ile doğruluk önemliyse kullanılır.
- **api-and-interface-design** — Kararlı API ve arayüz tasarımına rehberlik eder (REST/GraphQL uç noktaları, modüller arası tip sözleşmeleri, frontend-backend sınırları).
- **frontend-ui-engineering** — Üretim kalitesinde, erişilebilir, responsive kullanıcı arayüzleri inşa eder; WCAG gereksinimlerini karşılar.
- **subagent-driven-development** — Bağımsız görevleri içeren uygulama planlarını mevcut oturumda subagent'larla yürütür.
- **dispatching-parallel-agents** — Paylaşılan durum veya sıralı bağımlılık olmadan çalışılabilecek 2+ bağımsız görev olduğunda kullanılır.
- **using-git-worktrees** — Mevcut çalışma alanından izolasyon gerektiren özellik çalışmalarına başlarken izole bir çalışma alanı sağlar.

## Kalite ve İnceleme

- **code-review-and-quality** — Herhangi bir değişiklik ana dala birleştirilmeden önce çok eksenli kod incelemesi yapar.
- **code-simplification** — Davranışı değiştirmeden netlik için kodu sadeleştirir; kod çalışıyor ama gereksiz karmaşıklaşmışsa kullanılır.
- **requesting-code-review** — Görevleri tamamlarken, büyük özellikler uygularken veya birleştirmeden önce işin gereksinimleri karşıladığını doğrulamak için kullanılır.
- **receiving-code-review** — Kod inceleme geri bildirimi alırken, öneriler net değilse veya teknik olarak şüpheliyse, körü körüne uygulamak yerine teknik titizlik ve doğrulama gerektirir.
- **verification-before-completion** — İş bitti/düzeltildi/geçti demeden, commit/PR açmadan önce doğrulama komutlarını çalıştırıp çıktıyı onaylamayı zorunlu kılar.
- **debugging-and-error-recovery** — Testler başarısız olduğunda, build bozulduğunda veya beklenmeyen davranışlarda sistematik kök neden analizi yapar.
- **security-and-hardening** — Kullanıcı girdisi, kimlik doğrulama, veri depolama veya dış entegrasyonlarla çalışırken kodu güvenlik açıklarına karşı sağlamlaştırır.
- **performance-optimization** — Frontend, backend, sorgular ve veritabanlarında performansı optimize eder; N+1 sorgu, Core Web Vitals gibi durumlarda kullanılır.
- **browser-testing-with-devtools** — Chrome DevTools MCP üzerinden gerçek tarayıcılarda test yapar; DOM inceleme, konsol hataları, ağ istekleri, performans profili gerektirdiğinde kullanılır (chrome-devtools MCP sunucusu gerektirir).

## Sürüm Kontrolü ve Teslimat

- **git-workflow-and-versioning** — Commit, branch, çakışma çözümü, paralel iş akışları, sürüm bump'ı, etiketleme ve changelog yazımını yapılandırır.
- **finishing-a-development-branch** — Uygulama tamamlandığında, tüm testler geçtiğinde; merge/PR/temizlik seçeneklerini yapılandırılmış şekilde sunar.
- **ci-cd-and-automation** — CI/CD pipeline kurulumunu otomatikleştirir; kalite kapılarını, test çalıştırıcılarını, deployment stratejilerini yapılandırır.
- **shipping-and-launch** — Production'a deploy hazırlığı yapar: pre-launch checklist, monitoring kurulumu, aşamalı rollout, rollback stratejisi.
- **deprecation-and-migration** — Eski sistemleri/API'leri kaldırırken veya kullanıcıları bir uygulamadan diğerine taşırken yönetir.
- **observability-and-instrumentation** — Logging, metrik, tracing, alerting ekler; production'da çalışan özelliklerin kanıtlanabilir olmasını sağlar.
- **documentation-and-adrs** — Mimari kararları, API değişikliklerini, özellik teslimatlarını belgeler; gelecekteki mühendisler/agent'lar için bağlam kaydeder.

## Diğer

- **FlowForge** — Süreç, mimari veya kavramları çizmek/görselleştirmek istendiğinde (akış şeması, mimari diyagramı, karşılaştırma diyagramı vb.) kullanılır. Grafik/plot istekleri veya sanatsal görsel istekleri için DEĞİL.
- **writing-skills** — Yeni skill oluştururken, mevcut skill'leri düzenlerken veya dağıtımdan önce skill'lerin çalıştığını doğrularken kullanılır.

---
*Bu envanter `AllSkills.zip` (2026-08-06 tarihli) içeriğinden 2026-08-21'de oluşturulmuştur. Skill setinde değişiklik olursa bu dosyayı güncelleyin.*
