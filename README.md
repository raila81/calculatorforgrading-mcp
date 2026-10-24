# Calculator for Grading MCP server

Does the grade math students and teachers ask about most, with the same formulas as calculatorforgrading.com: the percent and letter grade from the number of questions wrong, the score needed on a final exam, weighted category averages, high school and college GPA, SAT, ACT and MCAT scores from published practice tests, and common US grading scales with named sources. It works with numbers and letter grades only and stores nothing.

- **Website:** [calculatorforgrading.com](https://calculatorforgrading.com)
- **Documentation:** [calculatorforgrading.com/ai-assistants/](https://calculatorforgrading.com/ai-assistants/)
- **Endpoint:** `https://calculatorforgrading.com/mcp` (MCP Streamable HTTP, public, no authentication, no API key)

## Tools

- `grade_calculator`: percent and letter from questions wrong
- `final_grade_needed`: score needed on the final
- `weighted_grade`: weighted average of categories
- `gpa_calculator`: GPA from letter grades and credits
- `test_score_calculator`: SAT, ACT and MCAT practice scores
- `grading_scale_facts`: grading scale cut-offs with sources

All tools are read-only and stateless. The server stores nothing it receives.

## Connect

Any MCP client that supports remote servers:

```json
{
  "mcpServers": {
    "calculatorforgrading": {
      "type": "streamable-http",
      "url": "https://calculatorforgrading.com/mcp?src=mcp"
    }
  }
}
```

Quick test:

```bash
curl -s -X POST 'https://calculatorforgrading.com/mcp?src=mcp' -H 'Content-Type: application/json' -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

This repository holds the listing metadata only. The server itself is a hosted service run by the Calculator for Grading website (https://calculatorforgrading.com); see the documentation link above for privacy and terms.
