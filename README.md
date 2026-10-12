<!doctype html>
<html lang="ar" dir="rtl">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>الكود الكامل لتطبيق قراءتي</title>
<style>
:root{color-scheme:light;--green:#216b45;--pale:#edf6ef;--ink:#20352a;--line:#d7e3da}
*{box-sizing:border-box}body{margin:0;background:#f6faf7;color:var(--ink);font-family:Arial,"Noto Sans Arabic",sans-serif;line-height:1.65}
header{background:var(--green);color:white;padding:26px 18px}header h1{margin:0 0 8px;font-size:26px}header p{margin:0;opacity:.94}
main{max-width:1000px;margin:0 auto;padding:18px}
.note{background:var(--pale);border:1px solid var(--line);border-radius:12px;padding:14px;margin:14px 0}
.file{background:white;border:1px solid var(--line);border-radius:12px;margin:16px 0;overflow:hidden}
.file-head{display:flex;align-items:center;justify-content:space-between;gap:10px;padding:12px 14px;background:#eef6f0;border-bottom:1px solid var(--line)}
h2{font-size:16px;margin:0;overflow-wrap:anywhere}
pre{direction:ltr;text-align:left;white-space:pre;overflow:auto;margin:0;padding:16px;font-size:13px;line-height:1.55;background:#fff;color:#17261d;tab-size:4}
code{font-family:Consolas,Monaco,monospace}
button{border:0;border-radius:8px;background:var(--green);color:white;padding:9px 13px;font-weight:bold;cursor:pointer;white-space:nowrap}
.download{display:inline-block;background:white;color:var(--green);text-decoration:none;padding:11px 16px;border-radius:8px;font-weight:bold;margin-top:14px}
footer{font-size:13px;color:#506457;padding:12px 0 30px}
</style>
</head>
<body>
<header><h1>الكود الكامل لتطبيق «قراءتي»</h1><p>ملفات المشروع مرتبة حسب مسار كل ملف، مع زر لنسخ الكود من الهاتف.</p><a class="download" href="Qiraati_Final_Source.zip" download>تنزيل ملفات المشروع ZIP</a></header>
<main>
<div class="note"><strong>ملاحظة:</strong> هذا ملف HTML لعرض ونسخ كود مشروع أندرويد. ليس تطبيق ويب بديلًا عن APK، ولا يُحوّل Kotlin إلى HTML؛ بل يجمع محتويات ملفات المشروع في صفحة واحدة.</div>

    <section class="file">
      <div class="file-head"><h2>settings.gradle</h2><button class="copy" onclick="copyCode(this)">نسخ الكود</button></div>
      <pre><code>pluginManagement { repositories { google(); mavenCentral(); gradlePluginPortal() } }
dependencyResolutionManagement { repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS); repositories { google(); mavenCentral() } }
rootProject.name = &quot;Qiraati&quot;
include(&quot;:app&quot;)
</code></pre>
    </section>

    <section class="file">
      <div class="file-head"><h2>build.gradle</h2><button class="copy" onclick="copyCode(this)">نسخ الكود</button></div>
      <pre><code>plugins {
    id &#x27;com.android.application&#x27; version &#x27;8.7.3&#x27; apply false
    id &#x27;org.jetbrains.kotlin.android&#x27; version &#x27;2.0.21&#x27; apply false
}
</code></pre>
    </section>

    <section class="file">
      <div class="file-head"><h2>gradle.properties</h2><button class="copy" onclick="copyCode(this)">نسخ الكود</button></div>
      <pre><code>org.gradle.jvmargs=-Xmx2048m -Dfile.encoding=UTF-8
android.useAndroidX=true
kotlin.code.style=official
</code></pre>
    </section>

    <section class="file">
      <div class="file-head"><h2>app/build.gradle</h2><button class="copy" onclick="copyCode(this)">نسخ الكود</button></div>
      <pre><code>plugins {
    id &#x27;com.android.application&#x27;
    id &#x27;org.jetbrains.kotlin.android&#x27;
}
android {
    namespace &#x27;com.example.qiraati&#x27;
    compileSdk 35
    defaultConfig {
        applicationId &#x27;com.example.qiraati&#x27;
        minSdk 23
        targetSdk 35
        versionCode 1
        versionName &#x27;1.0.0&#x27;
    }
}
dependencies {
    implementation &#x27;androidx.core:core-ktx:1.15.0&#x27;
    implementation &#x27;androidx.appcompat:appcompat:1.7.0&#x27;
}
</code></pre>
    </section>

    <section class="file">
      <div class="file-head"><h2>app/src/main/AndroidManifest.xml</h2><button class="copy" onclick="copyCode(this)">نسخ الكود</button></div>
      <pre><code>&lt;manifest xmlns:android=&quot;http://schemas.android.com/apk/res/android&quot;&gt;
    &lt;application android:allowBackup=&quot;true&quot; android:label=&quot;قراءتي&quot; android:supportsRtl=&quot;true&quot; android:theme=&quot;@style/AppTheme&quot;&gt;
        &lt;activity android:name=&quot;.MainActivity&quot; android:exported=&quot;true&quot;&gt;
            &lt;intent-filter&gt;
                &lt;action android:name=&quot;android.intent.action.MAIN&quot;/&gt;
                &lt;category android:name=&quot;android.intent.category.LAUNCHER&quot;/&gt;
            &lt;/intent-filter&gt;
        &lt;/activity&gt;
    &lt;/application&gt;
&lt;/manifest&gt;
</code></pre>
    </section>

    <section class="file">
      <div class="file-head"><h2>app/src/main/res/values/styles.xml</h2><button class="copy" onclick="copyCode(this)">نسخ الكود</button></div>
      <pre><code>&lt;resources&gt;
    &lt;style name=&quot;AppTheme&quot; parent=&quot;Theme.AppCompat.Light.NoActionBar&quot;&gt;
        &lt;item name=&quot;colorAccent&quot;&gt;#26734D&lt;/item&gt;
        &lt;item name=&quot;android:fontFamily&quot;&gt;sans&lt;/item&gt;
        &lt;item name=&quot;android:statusBarColor&quot;&gt;#174D35&lt;/item&gt;
        &lt;item name=&quot;android:navigationBarColor&quot;&gt;#174D35&lt;/item&gt;
        &lt;item name=&quot;android:windowLightStatusBar&quot;&gt;false&lt;/item&gt;
    &lt;/style&gt;
&lt;/resources&gt;
</code></pre>
    </section>

    <section class="file">
      <div class="file-head"><h2>app/src/main/java/com/example/qiraati/MainActivity.kt</h2><button class="copy" onclick="copyCode(this)">نسخ الكود</button></div>
      <pre><code>package com.example.qiraati

import android.app.Activity
import android.os.Bundle
import android.graphics.Color
import android.speech.tts.TextToSpeech
import android.speech.tts.UtteranceProgressListener
import android.text.Spannable
import android.text.SpannableString
import android.text.style.BackgroundColorSpan
import android.text.style.ForegroundColorSpan
import android.view.Gravity
import android.view.View
import android.widget.*
import android.content.res.ColorStateList
import java.util.Locale

class MainActivity : Activity(), TextToSpeech.OnInitListener {
    private lateinit var editor: EditText
    private lateinit var reader: TextView
    private lateinit var speed: SeekBar
    private lateinit var status: TextView
    private var tts: TextToSpeech? = null
    private var ttsReady = false
    private var words: List&lt;String&gt; = emptyList()
    private var ranges: List&lt;IntRange&gt; = emptyList()
    private var wordIndex = 0
    private var playing = false
    private var paused = false
    private var token = 0

    private val green = Color.rgb(31, 105, 68)
    private val darkGreen = Color.rgb(23, 77, 53)
    private val paleGreen = Color.rgb(235, 246, 238)
    private val yellow = Color.rgb(255, 224, 130)

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        window.statusBarColor = darkGreen
        window.navigationBarColor = darkGreen
        tts = TextToSpeech(this, this)
        buildUi()
    }

    private fun buildUi() {
        val root = LinearLayout(this).apply {
            orientation = LinearLayout.VERTICAL
            setPadding(dp(18), dp(14), dp(18), dp(12))
            setBackgroundColor(Color.rgb(248, 251, 248))
        }
        root.addView(TextView(this).apply {
            text = &quot;قراءتي&quot;
            textSize = 29f
            typeface = android.graphics.Typeface.DEFAULT_BOLD
            setTextColor(green)
            gravity = Gravity.CENTER
            setPadding(0, dp(5), 0, dp(8))
        }, matchWrap())
        root.addView(TextView(this).apply {
            text = &quot;اقرأ النصوص واستمع إليها ببطء&quot;
            textSize = 15f
            setTextColor(Color.DKGRAY)
            gravity = Gravity.CENTER
            setPadding(0, 0, 0, dp(10))
        }, matchWrap())

        editor = EditText(this).apply {
            hint = &quot;اكتب النص هنا أو الصقه...&quot;
            textSize = 18f
            gravity = Gravity.TOP or Gravity.START
            minLines = 4
            maxLines = 7
            setPadding(dp(12), dp(10), dp(12), dp(10))
            setBackgroundColor(Color.WHITE)
        }
        root.addView(editor, LinearLayout.LayoutParams(-1, 0, 1f))

        root.addView(TextView(this).apply {
            text = &quot;سرعة القراءة: بطيئة ← → سريعة&quot;
            textSize = 14f
            setTextColor(green)
            setPadding(0, dp(10), 0, 0)
        }, matchWrap())
        speed = SeekBar(this).apply { max = 8; progress = 2 }
        root.addView(speed, matchWrap())

        val row = LinearLayout(this).apply { orientation = LinearLayout.HORIZONTAL; gravity = Gravity.CENTER }
        row.addView(makeButton(&quot;▶ قراءة&quot;, green) { startOrResume() }, LinearLayout.LayoutParams(0, dp(48), 1f))
        row.addView(makeButton(&quot;Ⅱ مؤقت&quot;, Color.rgb(77, 119, 89)) { pauseReading() }, LinearLayout.LayoutParams(0, dp(48), 1f))
        row.addView(makeButton(&quot;■ إيقاف&quot;, Color.rgb(133, 78, 78)) { stopReading() }, LinearLayout.LayoutParams(0, dp(48), 1f))
        root.addView(row, LinearLayout.LayoutParams(-1, dp(54)))

        root.addView(TextView(this).apply {
            text = &quot;النص أثناء القراءة&quot;
            textSize = 18f
            typeface = android.graphics.Typeface.DEFAULT_BOLD
            setTextColor(green)
            setPadding(0, dp(8), 0, dp(6))
        }, matchWrap())

        reader = TextView(this).apply {
            text = &quot;سيظهر النص هنا مع تمييز الكلمة الحالية باللون الأصفر.&quot;
            textSize = 22f
            setTextColor(Color.rgb(39, 54, 44))
            setBackgroundColor(paleGreen)
            setPadding(dp(14), dp(14), dp(14), dp(14))
            textDirection = View.TEXT_DIRECTION_FIRST_STRONG
        }
        val scroll = ScrollView(this)
        scroll.addView(reader)
        root.addView(scroll, LinearLayout.LayoutParams(-1, 0, 1f))
        root.addView(TextView(this).apply {
            text = &quot;الترجمة غير متاحة في هذه النسخة.&quot;
            textSize = 12f
            setTextColor(Color.DKGRAY)
            setPadding(0, dp(6), 0, 0)
        }, matchWrap())
        status = TextView(this).apply {
            text = &quot;جارٍ تجهيز محرك الصوت...&quot;
            textSize = 13f
            setTextColor(green)
            setPadding(0, dp(4), 0, 0)
        }
        root.addView(status, matchWrap())
        setContentView(root)
    }

    private fun makeButton(label: String, color: Int, action: () -&gt; Unit) =
        Button(this).apply {
            text = label
            textSize = 11f
            isAllCaps = false
            setTextColor(Color.WHITE)
            backgroundTintList = ColorStateList.valueOf(color)
            setOnClickListener { action() }
        }

    private fun matchWrap() = LinearLayout.LayoutParams(-1, -2)
    private fun dp(v: Int) = (v * resources.displayMetrics.density).toInt()

    override fun onInit(result: Int) {
        if (result != TextToSpeech.SUCCESS) {
            status.text = &quot;تعذر تشغيل محرك تحويل النص إلى كلام.&quot;
            return
        }
        val lang = tts?.setLanguage(Locale(&quot;ar&quot;))
        ttsReady = lang != null &amp;&amp; lang != TextToSpeech.LANG_MISSING_DATA &amp;&amp;
            lang != TextToSpeech.LANG_NOT_SUPPORTED
        status.text = if (ttsReady) &quot;جاهز للقراءة باللغة العربية.&quot;
            else &quot;قد تحتاج إلى تثبيت صوت العربية من إعدادات تحويل النص إلى كلام.&quot;
    }

    private fun startOrResume() {
        if (!ttsReady) {
            status.text = &quot;محرك الصوت غير جاهز. تحقق من إعدادات تحويل النص إلى كلام.&quot;
            return
        }
        if (paused &amp;&amp; words.isNotEmpty()) {
            paused = false
            playing = true
            token++
            speakNext(token)
            return
        }
        val source = editor.text.toString().trim()
        if (source.isEmpty()) {
            status.text = &quot;اكتب نصًا أولًا ثم اضغط قراءة.&quot;
            return
        }
        tts?.stop()
        words = Regex(&quot;\\S+&quot;).findAll(source).map { it.value }.toList()
        ranges = Regex(&quot;\\S+&quot;).findAll(source).map { it.range.first..it.range.last }.toList()
        wordIndex = 0
        playing = true
        paused = false
        token++
        speakNext(token)
    }

    private fun speakNext(myToken: Int) {
        if (!playing || myToken != token) return
        if (wordIndex &gt;= words.size) {
            playing = false
            paused = false
            status.text = &quot;اكتملت القراءة.&quot;
            return
        }
        highlight(wordIndex)
        tts?.setSpeechRate(0.35f + speed.progress * 0.15f)
        tts?.setOnUtteranceProgressListener(object : UtteranceProgressListener() {
            override fun onStart(utteranceId: String?) {}
            override fun onDone(utteranceId: String?) {
                runOnUiThread {
                    if (playing &amp;&amp; myToken == token) {
                        wordIndex++
                        reader.postDelayed({ speakNext(myToken) }, 100)
                    }
                }
            }
            @Deprecated(&quot;Deprecated in Java&quot;)
            override fun onError(utteranceId: String?) {
                runOnUiThread { if (myToken == token) status.text = &quot;حدث خطأ أثناء النطق.&quot; }
            }
        })
        tts?.speak(words[wordIndex], TextToSpeech.QUEUE_FLUSH, null, &quot;qiraati_${myToken}_$wordIndex&quot;)
        status.text = &quot;الكلمة ${wordIndex + 1} من ${words.size}&quot;
    }

    private fun highlight(index: Int) {
        val source = editor.text.toString()
        if (index !in ranges.indices) return
        val r = ranges[index]
        if (r.first &lt; 0 || r.last &gt;= source.length) return
        val s = SpannableString(source)
        s.setSpan(BackgroundColorSpan(yellow), r.first, r.last + 1, Spannable.SPAN_EXCLUSIVE_EXCLUSIVE)
        s.setSpan(ForegroundColorSpan(Color.BLACK), r.first, r.last + 1, Spannable.SPAN_EXCLUSIVE_EXCLUSIVE)
        reader.text = s
    }

    private fun pauseReading() {
        if (!playing) {
            status.text = &quot;لا توجد قراءة جارية لإيقافها مؤقتًا.&quot;
            return
        }
        playing = false
        paused = true
        token++
        tts?.stop()
        status.text = &quot;تم الإيقاف المؤقت. اضغط قراءة للاستئناف.&quot;
    }

    private fun stopReading() {
        token++
        tts?.stop()
        playing = false
        paused = false
        wordIndex = 0
        status.text = &quot;تم إيقاف القراءة.&quot;
    }

    override fun onDestroy() {
        token++
        tts?.stop()
        tts?.shutdown()
        super.onDestroy()
    }
}
</code></pre>
    </section>

    <section class="file">
      <div class="file-head"><h2>.github/workflows/build-apk.yml</h2><button class="copy" onclick="copyCode(this)">نسخ الكود</button></div>
      <pre><code>name: Build Qiraati APK

on:
  workflow_dispatch:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: &#x27;17&#x27;
      - uses: gradle/actions/setup-gradle@v4
        with:
          gradle-version: &#x27;8.9&#x27;
      - name: Build debug APK
        run: gradle assembleDebug
      - uses: actions/upload-artifact@v4
        with:
          name: Qiraati-debug-apk
          path: app/build/outputs/apk/debug/app-debug.apk
          if-no-files-found: error
</code></pre>
    </section>

    <section class="file">
      <div class="file-head"><h2>README_AR.md</h2><button class="copy" onclick="copyCode(this)">نسخ الكود</button></div>
      <pre><code># قراءتي — مشروع أندرويد

## المميزات
- واجهة عربية خضراء.
- قراءة النص باستخدام محرك Android Text-to-Speech.
- ضبط سرعة الصوت.
- تمييز الكلمة الحالية.
- إيقاف مؤقت واستئناف وإيقاف.

## البناء من GitHub
1. ارفع محتويات المشروع إلى جذر المستودع، وليس ملف ZIP فقط.
2. تأكد من رفع `.github/workflows/build-apk.yml`.
3. افتح Actions ثم Build Qiraati APK ثم Run workflow.
4. بعد النجاح نزّل `Qiraati-debug-apk` من Artifacts، وفك ضغطه لتحصل على `app-debug.apk`.

## ملاحظات
هذه نسخة أولية لم تُختبر على أجهزة فعلية في هذه البيئة. الترجمة وحفظ النصوص غير مضافين.
</code></pre>
    </section>
<footer>يمكنك فتح الصفحة في متصفح الهاتف ونسخ كل ملف على حدة. عند رفع المشروع إلى GitHub، يجب وضع محتويات الملفات في المسارات الموضحة، وليس لصق جميع الأكواد في ملف واحد.</footer>
</main>
<script>
async function copyCode(button){
 const code=button.closest('.file').querySelector('code').innerText;
 try{await navigator.clipboard.writeText(code);button.textContent='تم النسخ ✓';}
 catch(e){const area=document.createElement('textarea');area.value=code;document.body.appendChild(area);area.select();document.execCommand('copy');area.remove();button.textContent='تم النسخ ✓';}
 setTimeout(()=>button.textContent='نسخ الكود',1800);
}
</script>
</body>
</html>
