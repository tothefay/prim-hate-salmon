NekoChat Studio — prototype

เริ่มใช้งาน:
1) แตกไฟล์ ZIP ไปยังโฟลเดอร์
2) เปิดผ่าน static web hosting หรือ localhost (แนะนำ HTTPS สำหรับ PWA)
3) ไปที่ API & โมเดล เพิ่ม Google AI Studio API Key
4) กดดึงรายชื่อโมเดล เลือกโมเดล แล้วสร้างตัวละครเพื่อเริ่มแชท

หมายเหตุสำคัญ:
- Google Gemini API ใช้ generateContent / streamGenerateContent ไม่ใช่ OpenAI Chat Completions endpoint โดยตรง
- API key ถูกเก็บใน IndexedDB ของเบราว์เซอร์เครื่องนี้ การใส่ key ในเว็บฝั่ง client มีความเสี่ยงหากนำเว็บไปเผยแพร่สาธารณะ ควรทำ backend proxy และเก็บ secrets ฝั่ง server สำหรับ production
- รองรับสตรีมมิ่งผ่าน SSE, หลาย API keys, ดึงโมเดลที่ API key มองเห็น, prompt, lorebook, regex, custom CSS, character/chat CRUD, branch, search, pin, export JSON
- การนำเข้า PNG ในรุ่นต้นแบบเก็บรูปเป็น avatar เท่านั้น ยังไม่ได้ parse embedded Tavern Card metadata; PNG export card, batch operations ข้ามห้อง, advanced regex pipelines และ PWA offline cache ควรทดสอบ/ต่อยอดก่อน production
- PWA ต้องเปิดผ่าน HTTPS หรือ localhost; service worker cache เป็น offline shell เท่านั้น การเรียก AI ยังต้องใช้อินเทอร์เน็ต
- Think budget ขึ้นกับความสามารถของโมเดลที่เลือก อาจถูกปฏิเสธโดยบางโมเดล.
