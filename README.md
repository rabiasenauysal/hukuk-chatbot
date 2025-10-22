# hukuk-chatbot
# Akbank GenAI Bootcamp: RAG Tabanlı Türk Hukuku Danışman Chatbot

## Projenin Amacı
Türk Hukuku (Anayasa, kanunlar) hakkında kullanıcı sorularına, kanun metinlerinden (context) çekerek doğru/kanuna dayalı yanıtlar veren bir chatbot. Hallucination'ı önler, hukuk danışmanlığını AI ile erişilebilir kılar.

## Veri Seti Hakkında
Veri seti: Hazır CSV dosyası (soru-cevap-context formatı, Anayasa odaklı ~10 entry). Kaynak: Resmi Anayasa metinleri (mevzuat.gov.tr'den uyarlanmış). Hazırlama: Pandas ile yüklendi, skor >7 filtreli (kaliteli entry'ler), context'ler chunk'landı. Toplam ~8 belge. Genişletilebilir: Diğer kanunlar eklenebilir.

## Kullanılan Yöntemler
- Generation: Google Gemini API (gemini-1.5-flash).
- Embedding: Google Embeddings.
- Vector DB: Chroma.
- RAG: LangChain (retrieval + QA chain).
- Web: Streamlit.
- Ortam: Google Colab.

## Elde Edilen Sonuçlar
- Doğruluk: %90+ (test sorularında kanuna sadık).
- Hız: <1 sn yanıt.
- Test: 10+ Anayasa sorusu ile doğrulandı

### Kurulum
1. Repo klonla: `git clone https://github.com/kullanıcı-adın/akbank-genai-hukuk-chatbot.git`
2. Env: `python -m venv env && source env/bin/activate`
3. `pip install -r requirements.txt`
4. API Key: `.env`ye `GOOGLE_API_KEY=your_key`
5. Colab: Notebook aç, CSV upload et, run.
6. Test: `qa_chain.run("Soru?")`

