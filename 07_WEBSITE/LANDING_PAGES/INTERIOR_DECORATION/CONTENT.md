# Interior Decoration — Landing Page Content

## Document Information

- **Owner:** Business Owner / Marketing
- **Status:** **Published.** Merged into `afaqalhayatae-app/src/lib/catalog/landing-pages.ts` and live at `/en/lp/interior-decoration` and `/ar/lp/interior-decoration`. See "Why this was held back, and how it was unblocked" below.
- **Prepared:** 2026-08-07 (as part of the same Owner-prioritized request that shipped `PAINTING/`, "عايزك تركز لي علي الصبغ والديكوات")
- **Published:** 2026-08-07 — held back same-day pending an explicit Owner activation decision (see below), then the Owner reviewed and approved directly in chat ("انشر") a few hours later.
- **Source facts:** `afaqalhayatae-app/src/data/SERVICE_DATABASE.json`'s `interior-decoration` entry — content itself is real and Owner-sourced (`status.pageContent`: "Draft — foundation content added 2026-08-04... NOT wired into `APPROVED_SERVICE_CONTENT_SLUGS`"). No fact below goes beyond what's already there.

## Why this was held back, and how it was unblocked

**Update 2026-08-07:** the reasoning below is why this page was not published when first drafted. It's kept as-is for the record. The Owner reviewed it in chat the same day and gave the explicit activation decision it called for ("انشر"), so the page was merged and published — see Document Information above. The `booking-options.ts` gap in point 4 was fixed at the same time.

Checked fresh against `00_GOVERNANCE/11_SERVICE_ACTIVATION_REVIEW.md` (2026-08-04) and `LANDING_PAGE_SYSTEM/PACKAGES/interior-decoration.md` before writing this file:

1. Interior Decoration is one of 11 "Service Expansion Phase" services (`DECISION_LOG.md` #39, structure/SEO-only approval). Its recommended activation order is **Phase 3a — "highest scope-ambiguity of the 11 — activate after Phase 1 signal is clean."**
2. Phase 1 (Smart Home Installation, Swimming Pool Maintenance, Interlock Installation, Wallpaper Installation) has not been activated anywhere on the live site yet — so Phase 3a's own prerequisite isn't met.
3. It is not in `APPROVED_SERVICE_CONTENT_SLUGS`, and per `LANDING_PAGE_SYSTEM/PACKAGES/README.md`: "none has been added to `APPROVED_SERVICE_CONTENT_SLUGS`, and no service is live/indexable as a result of these packages existing."
4. It has no matching entry in `afaqalhayatae-app/src/lib/catalog/booking-options.ts` — `getCategoryForServiceSlug("interior-decoration")` returns `null`, so a `/book?service=interior-decoration` visitor lands on the booking form without a pre-selected category (a real, if non-breaking, UX gap the Activation Review already flagged as cross-cutting for all 11).
5. Painting, by contrast, is one of the 16 already-complete, already-live catalog services with its own formal sign-off (`DECISION_LOG.md` #38, `PAINTING_CONTENT_APPROVAL_DECISION.md` / `_APPLIED.md`) — that's why it shipped today and this didn't.

**What would unblock this:** an explicit Owner activation decision for Interior Decoration specifically (the same formal sign-off pattern every other live service already has), ideally after Phase 1 of the 11 is live and monitored per the Activation Review's own plan. Once that exists, merging the block below into `landing-pages.ts` and adding the `INTERIOR_DECORATION/` row to the parent `README.md`'s table is the entire remaining step.

## Hero

**Eyebrow:** Interior Decoration / الديكور الداخلي

**Headline:** A Refined Finish for Every Room / لمسة تشطيب راقية لكل غرفة

**Subheadline:** Fixture installation, wall treatments, and finishing touches for homes and businesses — coordinated with painting and wallpaper trades where needed, across all 7 emirates. / تركيب التجهيزات ومعالجة الجدران ولمسات التشطيب للمنازل والمنشآت — بالتنسيق مع فرق الدهان وورق الحائط عند الحاجة، في جميع الإمارات السبع.

**Visible phone number:** +971 58 543 1766 (same pattern as every other page in this system, via the `UnifiedHero` `phone` prop added 2026-08-07)

**Trust Badges:** UAE-wide service / خدمة في جميع الإمارات | Trained technicians / فنيون مدربون | Available 24/7 / متاحون على مدار الساعة | Quality-focused / التركيز على الجودة

## Problem / Pain Point

### A Space That Feels Outdated Doesn't Need a Full Renovation / المساحة التي تبدو قديمة لا تحتاج ترميمًا كاملاً

Shelving that's never been mounted, molding left unfinished, or a color and material mix that never quite came together — these are finishing gaps, not structural problems, and they're usually simpler to resolve than they feel.

أرفف لم يتم تركيبها بعد، أو كرانيش غير مكتملة، أو مزيج ألوان ومواد لم يتناسق أبدًا — هذه فجوات تشطيب، وليست مشاكل إنشائية، وعادة ما تكون أبسط في الحل مما تبدو عليه.

A room needing a refresh before a specific occasion or handover, or existing decorative elements that are damaged or incomplete, are common reasons homeowners reach out — and coordinating paint, wallpaper, and fixtures into one consistent look is exactly the gap this service closes.

غرفة تحتاج تجديدًا قبل مناسبة معينة أو تسليم، أو عناصر ديكور موجودة تالفة أو غير مكتملة، من الأسباب الشائعة التي تدفع أصحاب المنازل للتواصل — وتنسيق الدهان وورق الحائط والتجهيزات في مظهر واحد متسق هو بالضبط ما تسده هذه الخدمة.

## Why Choose AFAQ AL HAYAT

### Why UAE Homeowners Choose AFAQ AL HAYAT / لماذا يختار أصحاب المنازل في الإمارات آفاق الحياة

- A coordinated finish across fixtures, wall treatments, and trim — not disconnected individual jobs.
- تشطيب منسق عبر التجهيزات ومعالجة الجدران والحواف — وليس أعمالًا منفصلة.
- A clear plan agreed with you before any work starts.
- خطة واضحة متفق عليها معك قبل بدء أي عمل.
- Careful, safe installation — especially for anything mounted at height.
- تركيب دقيق وآمن — خصوصًا لأي عنصر يُثبت على ارتفاع.
- Coverage across all 7 emirates.
- تغطية في جميع الإمارات السبع.

## Service Details

### What Our Interior Decoration Service Covers / ما الذي تشمله خدمة الديكور الداخلي لدينا

**Included:**

- Space assessment and desired-outcome discussion
- معاينة المساحة ومناقشة النتيجة المطلوبة
- Installation of decorative fixtures and fittings
- تركيب تجهيزات وقطع الديكور
- Coordination with painting/wallpaper trades for a combined finish
- التنسيق مع فرق الدهان وورق الحائط لتشطيب متكامل
- General finishing touches — trim, molding, fixture placement
- لمسات تشطيب عامة — حواف وكرانيش وأماكن التجهيزات

**Excluded (per `SERVICE_DATABASE.json`):** structural renovation or layout changes, furniture sourcing/selection (subject to company policy), specific designer/brand product sourcing. This exclusion list is deliberately kept visible on the page (in the FAQ), not buried — per the Activation Review's own note that this is the broadest-scope, highest-expectation-risk service of the 11.

## Our Process

### How It Works / كيف تسير الخدمة

**1. Assessment / ١. المعاينة** — Book online or message us — a technician assesses the space and desired outcome. احجز أونلاين أو راسلنا — يقوم الفني بمعاينة المساحة والنتيجة المطلوبة.
**2. Plan / ٢. الخطة** — A plan is agreed with you, coordinated with any other trades involved (painting, wallpaper). يتم الاتفاق على خطة معك، بالتنسيق مع أي فرق أخرى مشاركة (دهان، ورق حائط).
**3. Installation / ٣. التركيب** — Fixtures and finishing elements are installed. يتم تركيب التجهيزات وعناصر التشطيب.
**4. Walkthrough / ٤. الفحص النهائي** — A final walkthrough together before the team leaves. فحص نهائي معًا قبل مغادرة الفريق.

## Standard of Work

### The Standard You Can Expect / المستوى الذي يمكنك توقعه

Standard practice for mounting and fixing decorative elements safely — and any pre-existing wall or surface issue is reported to you, not concealed.

ممارسات معيارية لتركيب وتثبيت عناصر الديكور بأمان — وأي مشكلة موجودة مسبقًا في الحائط أو السطح يتم إبلاغك بها بدل إخفائها.

## Pricing Guidance

### What Does It Cost? / كم التكلفة؟

Pricing depends on the scope and the fixtures involved — get a free, no-obligation quote after a quick chat with our team.

التكلفة تعتمد على نطاق العمل والتجهيزات المطلوبة — احصل على عرض سعر مجاني وبدون التزام بعد محادثة سريعة مع فريقنا.

## Reviews

Honest placeholder — no invented testimonials: "Customer reviews will appear here as they come in." / "ستظهر آراء العملاء هنا فور توفرها." (9 real Google reviews, 5.0 stars, exist for the business overall as of 2026-08-07 — none specific to interior decoration, so none are force-fit onto this page.)

## FAQ

**1. Do you handle structural changes?**
No, structural renovation is outside this service's scope — assessed separately if needed.

**بتتعاملوا مع تغييرات إنشائية؟**
لا، الترميم الإنشائي خارج نطاق هذه الخدمة — يتم تقييمه بشكل منفصل عند الحاجة.

**2. Can you coordinate with painting or wallpaper work?**
Yes, coordination with those trades is part of the scope when a combined finish is needed.

**بتقدروا تنسقوا مع أعمال الدهان أو ورق الحائط؟**
نعم، التنسيق مع هذه الفرق جزء من نطاق الخدمة عند الحاجة لتشطيب متكامل.

**3. Do you source the decorative materials?**
Subject to company policy — discussed during the initial assessment.

**بتوفروا مواد الديكور؟**
يخضع ذلك لسياسة الشركة — يتم مناقشته أثناء المعاينة الأولية.

**4. Do you help choose or source furniture?**
Furniture sourcing and selection is subject to company policy and your preference — discussed during the initial assessment.

**بتساعدوا في اختيار أو توفير الأثاث؟**
توريد واختيار الأثاث يخضع لسياسة الشركة وتفضيلك — يتم مناقشته أثناء المعاينة الأولية.

**5. Can you source a specific designer or brand product I want?**
Sourcing a specific designer or brand product is outside this service's scope — we can discuss general alternatives during the assessment.

**بتقدروا توفروا منتج ماركة أو مصمم معين أطلبه؟**
توريد منتج ماركة أو مصمم معين خارج نطاق هذه الخدمة — يمكننا مناقشة بدائل عامة أثناء المعاينة.

**6. Is it safe to mount heavy decorative pieces on my walls?**
Our technicians follow standard practice for mounting and fixing decorative elements safely, especially at height.

**هل من الآمن تركيب قطع ديكور ثقيلة على جدراني؟**
يتبع فنيونا ممارسات معيارية لتركيب وتثبيت عناصر الديكور بأمان، خصوصًا على ارتفاع.

**7. Will I see a plan before you start any work?**
Yes — the plan is agreed with you first, coordinated with any other trades involved, before installation begins.

**هل سأرى خطة قبل بدء أي عمل؟**
نعم — يتم الاتفاق على الخطة معك أولاً، بالتنسيق مع أي فرق أخرى مشاركة، قبل بدء التركيب.

**8. Do you serve my emirate?**
We cover all 7 UAE emirates — Dubai, Abu Dhabi, Sharjah, Ajman, Umm Al Quwain, Ras Al Khaimah, and Fujairah.

**هل تقدمون الخدمة في إمارتي؟**
نغطي جميع إمارات الدولة السبع — دبي، أبوظبي، الشارقة، عجمان، أم القيوين، رأس الخيمة، والفجيرة.

**9. Can I book online without calling?**
Yes — use the booking form on this page, or message us on WhatsApp.

**هل يمكنني الحجز أونلاين بدون اتصال؟**
نعم — استخدم نموذج الحجز في هذه الصفحة، أو راسلنا عبر واتساب.

**10. Is AFAQ AL HAYAT available for emergencies?**
We're available 24/7 — reach out any time and our team will confirm the earliest available visit.

**هل آفاق الحياة متاحة للحالات الطارئة؟**
نحن متاحون على مدار الساعة — تواصل معنا في أي وقت وسيؤكد فريقنا أقرب موعد متاح.

## Final CTA

### Give Every Room a Finished, Coordinated Look / امنح كل غرفة مظهرًا متكاملاً ومنسقًا

Book online, call, or message us on WhatsApp — our team follows up to confirm your visit.

احجز أونلاين، أو اتصل، أو راسلنا عبر واتساب — يتابع فريقنا معك لتأكيد زيارتك.
