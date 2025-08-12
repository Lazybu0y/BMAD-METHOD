# code-quality-review

When a developer agent marks a story as "Ready for Review", perform a focused technical code review specifically targeting code quality, architecture, security, and performance before functional testing.

## Prerequisites

- Story status must be "Review"
- Developer has completed all tasks and updated the File List
- All automated tests are passing
- Code is ready for technical quality assessment

## Review Process

1. **Read the Complete Story**
   - Review all acceptance criteria
   - Understand the dev notes and requirements
   - Note any completion notes from the developer
   - Focus on technical implementation aspects

2. **Verify Implementation Against Architecture**
   - Review the "Dev Notes" section for architectural guidance
   - Verify adherence to established patterns and principles
   - Check integration points and dependencies
   - Validate file organization and structure

3. **Code Quality Deep Dive**
   - **Readability**: Code is clear, well-structured, and self-documenting
   - **Maintainability**: Easy to modify and extend without breaking changes
   - **SOLID Principles**: Single responsibility, open/closed, dependency injection
   - **Design Patterns**: Appropriate use of patterns, avoiding anti-patterns
   - **Code Duplication**: DRY principle adherence, proper abstraction
   - **Error Handling**: Comprehensive error handling and logging
   - **Resource Management**: Proper cleanup, memory management, connection handling

4. **Security Analysis**
   - **Input Validation**: All user inputs properly sanitized and validated
   - **Authentication/Authorization**: Proper access controls implemented
   - **Data Protection**: Sensitive data handling, encryption where needed
   - **Injection Attacks**: SQL injection, XSS, command injection prevention
   - **Dependencies**: Third-party libraries are secure and up-to-date
   - **Secrets Management**: No hardcoded credentials or API keys

5. **Performance Review**
   - **Algorithm Efficiency**: Optimal time and space complexity
   - **Database Queries**: Efficient queries, proper indexing considerations
   - **Caching Strategy**: Appropriate caching implementation
   - **Resource Usage**: Memory leaks, unnecessary computations
   - **Scalability**: Code can handle increased load
   - **Async/Concurrent**: Proper use of asynchronous patterns

6. **Technical Debt Assessment**
   - **Code Smells**: Long methods, large classes, feature envy
   - **Refactoring Opportunities**: Areas needing improvement
   - **Documentation**: Technical documentation completeness
   - **Testing**: Unit test quality and coverage gaps
   - **Configuration**: Hardcoded values that should be configurable

7. **Active Code Improvement**
   - As a lead code reviewer, you CAN and SHOULD make direct improvements
   - When making changes:
     - Refactor for better code quality
     - Add missing error handling
     - Optimize performance bottlenecks
     - Enhance security measures
     - Improve code structure and patterns
     - Update the File List if you modify additional files
     - Document all changes in Code Review Results

8. **Standards and Conventions**
   - Coding standards compliance
   - Naming conventions consistency
   - File organization adherence
   - Team-specific guidelines

## Update Story File - Code Review Results Section ONLY

**CRITICAL**: You are ONLY authorized to update the "Code Review Results" section of the story file. DO NOT modify any other sections.

After review and any improvements, append your results to the story file:

```markdown
## Code Review Results

### Review Date: [Date]
### Reviewed By: Alex (Lead Code Quality Engineer)

### Code Quality Assessment
[Overall technical quality rating: Excellent/Good/Needs Improvement/Poor]
[Summary of implementation quality from technical perspective]

### Security Analysis
- **Input Validation**: [✓/✗/N/A] [findings]
- **Authentication/Authorization**: [✓/✗/N/A] [findings]
- **Data Protection**: [✓/✗/N/A] [findings]
- **Injection Prevention**: [✓/✗/N/A] [findings]
- **Dependencies**: [✓/✗/N/A] [findings]
- **Secrets Management**: [✓/✗/N/A] [findings]

### Performance Analysis
- **Algorithm Efficiency**: [✓/✗/N/A] [findings]
- **Database Optimization**: [✓/✗/N/A] [findings]
- **Caching Strategy**: [✓/✗/N/A] [findings]
- **Resource Management**: [✓/✗/N/A] [findings]
- **Scalability**: [✓/✗/N/A] [findings]

### Code Quality Metrics
- **Readability**: [✓/✗] [score/notes]
- **Maintainability**: [✓/✗] [score/notes]
- **SOLID Principles**: [✓/✗] [adherence notes]
- **Design Patterns**: [✓/✗] [pattern usage notes]
- **Error Handling**: [✓/✗] [completeness notes]

### Technical Improvements Made
[List improvements you performed directly]
- **File**: [filename]
  - **Improvement**: [what was improved]
  - **Rationale**: [technical reason for improvement]
  - **Impact**: [how it improves code quality/security/performance]

### Technical Debt Identified
[Issues requiring attention]
- [ ] [High Priority] [Description of technical debt item]
- [ ] [Medium Priority] [Description of technical debt item]
- [ ] [Low Priority] [Description of technical debt item]

### Recommendations for Future Development
[Suggestions for ongoing improvement]

### Architecture Compliance
- **Design Patterns**: [✓/✗] [compliance notes]
- **Project Structure**: [✓/✗] [organization notes]
- **Integration Points**: [✓/✗] [dependency notes]

### Final Technical Assessment
[✓ Code Quality Approved - Ready for QA Testing] / [✗ Technical Issues Require Resolution]

### Notes for QA Agent
[Any technical context that would be helpful for functional testing]
```

## Key Principles

- Focus on TECHNICAL quality, not functional requirements (QA handles that)
- You are the technical quality gatekeeper before functional testing
- Make direct improvements for significant technical issues
- Balance between quality and delivery timeline
- Provide constructive technical guidance for learning
- Consider long-term maintainability and scalability

## Blocking Conditions

Stop the review and request clarification if:

- Code has critical security vulnerabilities
- Performance issues would impact production
- Architecture violations that compromise system integrity
- Technical debt that would significantly impact future development
- Missing critical error handling that could cause system instability

## Integration with QA Workflow

After code review completion:

1. **If Approved**: Story progresses to QA agent for functional testing
2. **If Issues Found**: Dev agent addresses technical issues before QA review
3. **Handoff Notes**: Provide technical context to help QA focus their testing

## Completion

After technical review:

1. If technically sound: Mark as "Code Quality Approved" for QA handoff
2. If issues remain: Keep in "Review" status with specific technical requirements
3. Always explain technical decisions and improvements for team learning