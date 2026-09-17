<div dir="rtl" style="text-align: right;">

# طابور الأوردرات المشحونة — Shipped Orders

![worker](https://img.shields.io/badge/worker-v1.1.0-blue)

**Worker بس — مفيش واجهة في الريبو ده.**

بترجّع الأوردرات اللي حالتها **`Shipped`** — يعني خرجت و**محدش سجّل لها نتيجة
نهائية** (`Delivered` / `Returned`) لسه، في الشحنة الأصلية
(`custom.manual_status`) أو دورة الاستبدال/الاسترجاع (`custom.status_2_r_e`).

> 🔴 **والطابور بيبدأ من أوردرات `01/04/2026`** (قرار أحمد · 17-09-2026) —
> الاستعلام فيه أرضية `created_at` جنب شرط الحالة، واللي أقدم من كده
> **مابيتجابش**. ⚠️ وأثرها هنا أكبر من طابور «جاهز»: ده الطابور اللي
> **بيتراكم**، فالصف اللي «نسي حد يقفله» من قبل التاريخ ده مابقاش بيبان
> هنا خالص.

> 🟡 **`In-Return` مش في الطابور** — بند مفتوح مستني قرار (التفاصيل في `CLAUDE.md`).

🔗 **الواجهة:** https://ecommoda-dev.github.io/Delivery-COD-Operations-Center/shipped-orders.html
(صفحة `shipped-orders.html` جوّه ريبو `Delivery-COD-Operations-Center`)

> ⛔ **ممنوع يتضاف `index.html` هنا.** الأداة **مالهاش نسخة مستقلة بقرار**
> (أحمد · 15-09-2026) — الدخول بيحصل مرة واحدة في الهب، والسر سر مجموعة
> `delivery_cod_ops`.

> 🔴 **قراءة بحتة** — صفر كتابة على شوبيفاي، وصفر صف في D1، ومفيش
> `[[d1_databases]]` أصلاً.

## Endpoints

```
GET  ?action=get_config        نسخة الـ Worker
GET  ?action=diag              فحص ذاتي بلا كتابة
GET  ?action=get_shipped_queue أوردرات Shipped (الماكينتين) بحقولها الخام
```

## النشر

منشور من git عبر **Workers Builds** على `main`.
الأسرار من الداشبورد ثم **Promote**: `WORKER_SECRET` (= سر مجموعة
`delivery_cod_ops`) · `CLIENT_ID` · `CLIENT_SECRET`.

التفاصيل والقرارات والفخاخ → **`CLAUDE.md`**

</div>
