# Multimodal AI Assignment - OpenAI Edition

This repository contains a comprehensive Google Colab notebook demonstrating multimodal AI capabilities using **OpenAI's GPT-4, GPT-4 Vision, and DALL-E 3 APIs**.

## 📋 Assignment Overview

This assignment covers three main components:

1. **Text-to-Image Generation** - Creating visual content using DALL-E 3
2. **Vision Analysis (Image-to-Text)** - Extracting information using GPT-4 Vision
3. **Advanced Conversational AI** - Engaging interactions using GPT-4

## 🚀 Quick Start

### Prerequisites
- Google account (for Colab)
- OpenAI account with API access
- **Payment method required** (credit/debit card)
- Recommended budget: $10-20 for complete assignment

### Setup Steps

1. **Get OpenAI API Key** (see detailed guide in `OpenAI_API_Key_Guide.md`)
   - Go to: https://platform.openai.com/api-keys
   - Create new secret key
   - Copy and store securely

2. **Open Notebook in Colab**
   - Upload `openai_multimodal_assignment.ipynb` to Google Colab
   - Or use: File → Upload notebook

3. **Add API Key to Colab Secrets**
   - Click 🔑 icon on left sidebar
   - Add secret: `OPENAI_API_KEY`
   - Paste your API key
   - Enable the secret

4. **Set Usage Limits** (Important!)
   - Go to: https://platform.openai.com/account/limits
   - Set monthly limit: $10-20
   - Enable email alerts

5. **Run the Notebook**
   - Runtime → Run all
   - Or run cells individually

## 💰 Cost Estimate

**Typical costs for running the entire notebook:**

| Component | Operations | Estimated Cost |
|-----------|-----------|----------------|
| DALL-E 3 Image Generation | 3 HD images | $0.24 |
| GPT-4 Vision Analysis | 5 image analyses | $0.50 |
| GPT-4 Conversations | ~10,000 tokens | $0.50 |
| **Total Estimated** | | **$1-2** |

**Recommended initial budget: $10-20** (provides buffer for experimentation)

## 📚 What's Included

### Part 1: Text-to-Image Generation (DALL-E 3)

**3 Complete Examples:**
1. **Futuristic Cityscape** - Bioluminescent city in clouds
2. **Surreal Nature** - Crystal tree with glowing river
3. **Fantasy Scene** - Underwater library with mermaids

**Features:**
- High-quality image generation
- Automatic prompt refinement by DALL-E 3
- Standard and HD quality options
- Multiple size options (1024×1024, 1792×1024, etc.)

### Part 2: Vision Analysis (GPT-4 Vision)

**3 Comprehensive Examples:**

**Example 1: Complex Scene Analysis**
- Detailed visual description
- Emotional and artistic interpretation
- Storytelling and narrative analysis
- Creative scenarios

**Example 2: Data Visualization Analysis**
- Multi-panel chart interpretation
- Trend identification
- Statistical insights
- Business recommendations

**Example 3: OCR and Document Analysis**
- Receipt text extraction
- Structured data extraction (JSON)
- Information verification
- Automated processing

### Part 3: Advanced Conversational AI (GPT-4)

**5 Diverse Examples:**

1. **Complex Problem Solving**
   - Smart city system design
   - Budget optimization
   - Risk assessment
   - Implementation planning

2. **Creative Writing**
   - Sci-fi short story (600-800 words)
   - Character development
   - Hard science elements
   - Philosophical themes

3. **Multi-Turn Code Review**
   - Neural network debugging
   - Backpropagation implementation
   - Advanced features (dropout, batch norm)
   - Context retention across turns

4. **Ethical Analysis**
   - Multi-stakeholder perspectives
   - Legal and regulatory considerations
   - Balanced reasoning
   - Policy recommendations

5. **Mathematical Optimization**
   - Multi-step calculations
   - Resource optimization
   - Cost-benefit analysis
   - Decision frameworks

## 🛠️ Technical Requirements

### Software
- Python 3.7+
- Google Colab (recommended) or Jupyter Notebook
- OpenAI Python library (v1.0+)

### Python Packages (auto-installed)
```bash
openai>=1.0.0
pillow
requests
matplotlib
numpy
```

### API Requirements
- OpenAI API key (required)
- Active billing account
- Usage limits configured

## 🔑 API Key Management

### Security Best Practices

✅ **DO:**
- Store in Colab Secrets
- Use environment variables
- Set usage limits
- Monitor spending
- Rotate keys regularly

❌ **DON'T:**
- Commit to GitHub
- Share publicly
- Hard-code in files
- Use in client-side code
- Share across projects

### Setting Up Colab Secrets

```python
# In Colab, this automatically reads from secrets
from google.colab import userdata
from openai import OpenAI

OPENAI_API_KEY = userdata.get('OPENAI_API_KEY')
client = OpenAI(api_key=OPENAI_API_KEY)
```

## 📊 Usage Monitoring

### Track Your Spending

1. **Real-time Dashboard**
   - https://platform.openai.com/usage
   - View daily/monthly costs
   - Model-specific breakdown

2. **Set Alerts**
   - 75% of limit warning
   - 90% of limit warning
   - 100% limit reached

3. **Usage Limits**
   - Set monthly caps
   - Prevent overages
   - Control spending

## 🎯 Assignment Checklist

- [x] Part 1: Image generation with DALL-E 3
- [x] Part 2: Vision analysis with GPT-4 Vision (3 examples)
- [x] Part 3: Advanced conversations with GPT-4 (5 examples)
- [x] Uses latest OpenAI models
- [x] Includes diverse, interesting examples
- [x] Proper error handling
- [x] Security best practices
- [x] Cost optimization tips
- [x] Clear documentation

## 💡 Key Features

✅ **Production Ready** - Complete error handling and validation  
✅ **Cost Optimized** - Efficient token usage and model selection  
✅ **Well Documented** - Detailed explanations and comments  
✅ **Security Focused** - Secure API key management  
✅ **Comprehensive** - Covers all assignment requirements  
✅ **Educational** - Learning-focused with best practices  

## 📖 Example Usage

### Generate an Image
```python
from openai import OpenAI

client = OpenAI(api_key="your-key")

response = client.images.generate(
    model="dall-e-3",
    prompt="A futuristic city in the clouds",
    size="1024x1024",
    quality="hd",
    n=1
)

image_url = response.data[0].url
```

### Analyze an Image
```python
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {
            "role": "user",
            "content": [
                {"type": "text", "text": "What's in this image?"},
                {"type": "image_url", "image_url": {"url": image_url}}
            ]
        }
    ]
)

print(response.choices[0].message.content)
```

### Chat with GPT-4
```python
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "user", "content": "Explain quantum computing"}
    ]
)

print(response.choices[0].message.content)
```

## 🔗 Useful Links

### OpenAI Resources
- [OpenAI Platform](https://platform.openai.com/)
- [API Documentation](https://platform.openai.com/docs)
- [GPT-4 Vision Guide](https://platform.openai.com/docs/guides/vision)
- [DALL-E Guide](https://platform.openai.com/docs/guides/images)
- [Pricing](https://openai.com/pricing)
- [Playground](https://platform.openai.com/playground)

### Learning Resources
- [Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
- [Best Practices](https://platform.openai.com/docs/guides/production-best-practices)
- [Community Forum](https://community.openai.com/)

## 🐛 Troubleshooting

### Common Issues and Solutions

**"Invalid API key"**
- Check key format (starts with `sk-`)
- Verify no extra spaces
- Ensure key not deleted
- Create new key if needed

**"Insufficient credits"**
- Add funds to account
- Check billing page
- Verify payment method

**"Rate limit exceeded"**
- Wait between requests
- Implement delays
- Upgrade tier if needed

**"Model not found"**
- Use correct model name: `gpt-4o`, `dall-e-3`
- Check account access
- Verify model availability

## 💸 Cost Optimization Tips

1. **Use GPT-3.5 for Testing**
   - Much cheaper (~$0.50 vs $2.50 per 1M input tokens)
   - Good for development

2. **Limit Response Length**
   ```python
   max_tokens=500  # Limit output
   ```

3. **Choose Appropriate Quality**
   ```python
   quality="standard"  # vs "hd" for DALL-E
   detail="low"  # vs "high" for GPT-4 Vision
   ```

4. **Cache Responses**
   - Store results
   - Avoid re-running same queries

5. **Monitor Usage**
   - Check dashboard regularly
   - Set spending alerts
   - Review monthly costs

## 🤝 Contributing

Suggestions for improvement:
- Add more examples
- Optimize prompts
- Reduce costs
- Improve documentation
- Report issues

## 📝 Notes

### Important Reminders

1. **Payment Required**: OpenAI API requires payment details (unlike free tiers of other services)

2. **Monitor Costs**: Always set usage limits and alerts

3. **API Key Security**: Never commit keys to version control

4. **Model Selection**:
   - GPT-4o: Vision + complex reasoning
   - GPT-3.5-Turbo: Simple tasks, cheaper
   - DALL-E 3: Image generation

5. **Free Credits**: New accounts may receive $5 in credits

## 📄 License

This project is for educational purposes. Please respect:
- OpenAI's Terms of Service
- API usage policies
- Copyright of generated content
- Ethical AI guidelines

## 🎓 Learning Outcomes

After completing this notebook, you will:

✅ Understand how to use OpenAI's multimodal APIs  
✅ Master prompt engineering for different tasks  
✅ Know how to analyze images with AI  
✅ Create complex multi-turn conversations  
✅ Implement cost-effective API usage  
✅ Follow security best practices  

---

## 📧 Support

For issues:
1. Check the troubleshooting section
2. Review [OpenAI documentation](https://platform.openai.com/docs)
3. Visit [Community Forum](https://community.openai.com/)
4. Check [Status Page](https://status.openai.com/)

---

**Ready to Explore OpenAI's Capabilities! 🚀**

*Last Updated: February 2025*

---

## Comparison: OpenAI vs Google Gemini

| Feature | OpenAI | Google Gemini |
|---------|--------|---------------|
| **Image Generation** | ✅ DALL-E 3 (Built-in) | ❌ Use external APIs |
| **Vision Analysis** | ✅ GPT-4 Vision | ✅ Gemini Pro Vision |
| **Text Quality** | ✅ GPT-4 | ✅ Gemini Pro |
| **Free Tier** | ❌ Payment required | ✅ Generous free tier |
| **Image Quality** | ✅ DALL-E 3 (High quality) | N/A |
| **Context Length** | ✅ 128k tokens | ✅ 1M+ tokens |
| **Cost** | $$ Medium | $ Lower |
| **Setup** | Requires payment | Just API key |

**Choose OpenAI if:** You need DALL-E image generation or prefer GPT-4's conversational quality

**Choose Gemini if:** You want free tier or need longer context windows
