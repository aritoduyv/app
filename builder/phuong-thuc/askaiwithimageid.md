---
description: Hỏi AI với ảnh đã có trên server dựa vào fileId, phiên bản >= 1.3.5
---

# askAIWithImageId

**Return type:**  {result}:{result:string | null}, giá trị AI trả lời

**Arguments:** ({fileId, imageUrlType, model, prompt, apiKey, max\_image\_dimession, responseSchema, callback})

* **fileId:** string, required, filedId của ảnh cần phần tích
* **imageUrlType**: string, required, loại ảnh, ví dụ private0, private1, public200
* **prompt:** string, required, câu hỏi cần hỏi AI
* **apiKey:** string, required, gemini token&#x20;
* **max\_image\_dimession**: string, required, Độ dài cạnh tối đa ảnh sau khi đã resize, lưu ý nếu ảnh nhỏ hơn thì sẽ không bị resize
* **responseSchema:** json, optional, hỏi với cấu trúc, AI sẽ trả về dạng json , tham khảo thêm tại [https://aistudio.google.com/app/u/0/prompts/new\_chat](https://aistudio.google.com/app/u/0/prompts/new_chat)
* **callback:** ({result})
  * **result:** string|null, kết quả trả về từ AI

**Example:**

```javascript
 p.askAIWithImageId({
     fileId: "80bb636480ee4810a30e86028430b2af",
     imageUrlType: "private0",
     model: "gemini-2.0-flash",
     prompt: "give me weight and unit",
     apiKey: "Aiza...",
     max_image_dimession: 500,
     responseSchema: {
         type: "object",
         properties: {
             weight: {
                 type: "number"
             },
             unit: {
                 type: "string"
             }
         },
         required: [
             "weight",
             "unit"
         ]
     },
     callback: ({ 
         result
     }) => {
         alert(result)
     }
 });
```

