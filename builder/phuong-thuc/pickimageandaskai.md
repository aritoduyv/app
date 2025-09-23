---
description: Hỏi AI với ảnh đã có trên server dựa vào fileId, phiên bản >= 1.3.5
---

# pickImageAndAskAI

**Return type:**  {result, localUri}: {result|null, localUri: string}, giá trị AI trả lời

**Arguments:** ({ model, prompt, apiKey, max\_image\_dimession, responseSchema, callback})&#x20;

* **model:** string, model sẽ sử dụng, ví dụ gemini-2.0-flash
* **prompt:** string, required, câu hỏi cần hỏi AI
* **apiKey:** string, required, gemini token&#x20;
* **max\_image\_dimession**: string, required, Độ dài cạnh tối đa ảnh sau khi đã resize, lưu ý nếu ảnh nhỏ hơn thì sẽ không bị resize
* **responseSchema:** json, optional, hỏi với cấu trúc, AI sẽ trả về dạng json , tham khảo thêm tại [https://aistudio.google.com/app/u/0/prompts/new\_chat](https://aistudio.google.com/app/u/0/prompts/new_chat)
* **callback:** ({localUri, result})
  * **result:** string|null, kết quả trả về từ AI
  * **localUri:** string, link ảnh tạm thời trên app sau khi đã resize

**Example:**

```javascript
p.pickImageAndAskAI({
    model: "gemini-2.0-flash",
    prompt: "give me weight and unit",
    apiKey: "AIza",
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
        localUri,
        result
    }) => {
        alert(result)
    }
});
```

