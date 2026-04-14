# Code Review Report

## Overview

**Review Date**: {{DATE}}
**Reviewer**: {{REVIEWER}}
**Files Reviewed**: {{FILE_COUNT}} files, {{LINE_COUNT}} lines changed
**Overall Assessment**: {{STATUS}}

---

## Executive Summary

{{BRIEF_SUMMARY}}

---

## Critical Issues ❌

Issues that must be addressed before merging:

### 1. {{ISSUE_TITLE}}

**File**: {{FILE_PATH}}:{{LINE_NUMBER}}  
**Severity**: Critical  
**Category**: {{SECURITY|PERFORMANCE|BUG}}

**Description**:
{{ISSUE_DESCRIPTION}}

**Current Code**:
```{{LANGUAGE}}
{{CODE_SNIPPET}}
```

**Suggested Fix**:
```{{LANGUAGE}}
{{SUGGESTED_CODE}}
```

**Rationale**:
{{WHY_THIS_MATTERS}}

---

## Warnings ⚠️

Issues that should be addressed (not blocking):

### 1. {{WARNING_TITLE}}

**File**: {{FILE_PATH}}:{{LINE_NUMBER}}  
**Severity**: Medium  
**Category**: {{MAINTAINABILITY|STYLE|TESTING}}

**Description**:
{{WARNING_DESCRIPTION}}

**Suggestion**:
{{IMPROVEMENT_SUGGESTION}}

---

## Suggestions 💡

Optional improvements for consideration:

- {{SUGGESTION_1}}
- {{SUGGESTION_2}}
- {{SUGGESTION_3}}

---

## Positive Highlights ✨

Things done well in this change:

- {{POSITIVE_1}}
- {{POSITIVE_2}}
- {{POSITIVE_3}}

---

## Metrics

| Metric | Value | Target | Status |
|--------|-------|--------|--------|
| Test Coverage | {{%}} | 70% | {{✅|⚠️|❌}} |
| Cyclomatic Complexity (avg) | {{VALUE}} | < 10 | {{✅|⚠️|❌}} |
| Max Function Length | {{LINES}} | < 50 | {{✅|⚠️|❌}} |
| Security Issues | {{COUNT}} | 0 | {{✅|⚠️|❌}} |
| Code Duplication | {{%}} | < 5% | {{✅|⚠️|❌}} |

---

## Risk Assessment

**Overall Risk Level**: {{LOW|MEDIUM|HIGH}}

### Factors

- **Security Impact**: {{LOW|MEDIUM|HIGH}}
- **Performance Impact**: {{LOW|MEDIUM|HIGH}}
- **Breaking Changes**: {{YES|NO}}
- **Data Migration Required**: {{YES|NO}}
- **Rollback Complexity**: {{LOW|MEDIUM|HIGH}}

### Mitigation Recommendations

{{RISK_MITIGATION_STEPS}}

---

## Testing Recommendations

- [ ] {{TEST_RECOMMENDATION_1}}
- [ ] {{TEST_RECOMMENDATION_2}}
- [ ] {{TEST_RECOMMENDATION_3}}

---

## Follow-up Actions

- [ ] {{ACTION_ITEM_1}}
- [ ] {{ACTION_ITEM_2}}
- [ ] {{ACTION_ITEM_3}}

---

## Reviewer Notes

{{ADDITIONAL_CONTEXT_OR_NOTES}}

---

## Approval Status

- [ ] ✅ **Approved** - Ready to merge
- [ ] ⚠️ **Approved with Minor Changes** - Can merge after addressing warnings
- [ ] ❌ **Changes Requested** - Must address critical issues before re-review

**Next Steps**: {{WHAT_AUTHOR_SHOULD_DO}}
