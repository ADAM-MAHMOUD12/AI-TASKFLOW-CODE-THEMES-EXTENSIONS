# THEMES CODING v1

دليل واجهة ثيمات AI TaskFlow الثابتة. الملف هو JSON بيانات فقط؛ لا JavaScript ولا CSS تنفيذي.

## قالب صالح

```json
{
  "name": "My Theme",
  "glass": true,
  "colors": {
    "editorBackground": "#edf4f8",
    "sidebarBackground": "#d9e7f0",
    "panelBackground": "#e4eef4",
    "foreground": "#183044",
    "accent": "#1677b8"
  },
  "sizes": {
    "uiFontSize": 13,
    "editorFontSize": 14,
    "cornerRadius": 10
  }
}
```

## واجهة المحرك

- `name`: اسم من 1 إلى 80 حرفًا.
- `glass`: قيمة منطقية؛ تفعيل طبقات الزجاج المدعومة من TaskFlow.
- `colors`: مفاتيح اختيارية من القائمة الثابتة أدناه. كل قيمة لون بصيغة `#RRGGBB`.
- `sizes`: إعدادات اختيارية رقمية بحدود لمنع القيم التي تكسر الواجهة:
  - `uiFontSize`: من 11 إلى 18 بكسل.
  - `editorFontSize`: من 10 إلى 24 بكسل.
  - `cornerRadius`: من 0 إلى 18 بكسل.

## مفاتيح الألوان المعتمدة

| المفتاح | الجزء المتأثر |
|---|---|
| `editorBackground`, `editorLineNumberForeground`, `editorCursorForeground`, `editorSelectionBackground`, `editorLineHighlightBackground`, `editorWhitespaceForeground` | مساحة التحرير والتحديد والمؤشر |
| `sidebarBackground`, `sidebarForeground`, `activityBarBackground`, `activityBarForeground` | الشريط الجانبي وشريط الأنشطة |
| `tabBarBackground`, `tabActiveBackground`, `tabActiveForeground`, `tabInactiveBackground`, `tabInactiveForeground` | شريط التبويبات وحالاته |
| `panelBackground`, `statusBarBackground`, `statusBarForeground` | اللوحات وشريط الحالة |
| `foreground`, `accent`, `focusBorder`, `inputBackground`, `inputForeground`, `buttonBackground`, `buttonForeground` | النص والتفاعل والحقول والأزرار |

تُرفض المفاتيح غير المعروفة وقيم اللون أو الحجم خارج الصيغة والحدود. يمكن حذف أي قيمة اختيارية ليستخدم المحرر قيمه الافتراضية.

## تجربة واعتماد الثيم

1. أنشئ ملف JSON حسب القالب، ثم استورده من Appearance.
2. استخدم **معاينة حية** في بطاقة المتجر لمراجعة الألوان والحجم.
3. ألغِ المعاينة للرجوع إلى المظهر السابق، أو اختر **تطبيق السمة** لحفظها.
4. استخدم **إعادة الشكل الأصلي** لاستعادة قيم TaskFlow الأصلية.

المعاينة مؤقتة. التطبيق يحفظ قيم المحرر السابقة حتى يتمكن من إعادتها.

## حدود التخصيص الآمن

هذه الواجهة لا تنفذ كودًا من ملفات الثيمات ولا تحمّل CSS أو مكتبات JavaScript عشوائية. هذا يجعل الثيمات قابلة للفحص والتراجع ويمنع الثيم من كسر بنية المحرر. لإضافة نقطة تخصيص جديدة، أضف token موثقًا إلى المحرك واختبر نطاقه قبل اعتماده؛ لا تتجاوز القائمة المعتمدة عبر خصائص CSS أو روابط خارجية.

إضافات VSIX مختلفة عن الثيمات: يستطيع ناشر الإضافة تعريف خيارات الألوان والأحجام والسلوك عبر `contributes.configuration` في `package.json`. بعد تثبيتها، افتح **إعدادات الإضافة** من المتجر؛ يستخدم TaskFlow محرر إعدادات Theia الأصلي لعرض الخيارات التي أعلنتها الإضافة. راجع كود الإضافة ومصدرها قبل التثبيت، لأن VSIX تنفذ كودًا ويمكنها الوصول إلى موارد المحرر.

لا يمكن ضمان خلو أي إضافة خارجية من الأخطاء بنسبة 100%. صيغة الثيمات تمنع الكود التنفيذي وتتحقق من القيم، بينما تظل الإضافات البرمجية بحاجة إلى مراجعة واختبار.
