Create or fix production-ready .NET repositories with comprehensive best practices orchestration:

[Extended thinking: This workflow orchestrates specialized agents to either create new .NET repositories from scratch or audit and remediate existing ones. It ensures environment validation, proper architecture, testing, CI/CD, and developer experience are all addressed systematically.]

## For NEW Repository Creation

### Phase 1: Environment Setup & Architecture

1. **Environment Validation**
   - Check .NET SDK version: `dotnet --version`
   - Check Azure Functions Core Tools (if applicable): `func --version`
   - Provide installation commands if missing
   - DO NOT proceed until environment is validated

2. **Solution Architecture**
   - Use Task tool with subagent_type="dotnet-solution-architect"
   - Prompt: "Design a .NET solution structure for: $ARGUMENTS. Include solution file, project organization, and technology recommendations. Specify if this includes Azure Functions, web APIs, or console applications."
   - Output: Solution structure, project layout, dotnet CLI commands

### Phase 2: Implementation Foundation

3. **Azure Functions Setup (if applicable)**
   - Use Task tool with subagent_type="azure-functions-engineer"
   - Prompt: "Create Azure Functions project for: $ARGUMENTS. Use the solution structure from previous step. Include triggers, bindings, local.settings.json, and host.json configuration."
   - Output: Function implementations, configuration files, deployment guidance

4. **Core Implementation**
   - Use Task tool with subagent_type="csharp-pro"
   - Prompt: "Implement core business logic for: $ARGUMENTS. Follow the architecture from previous steps. Include dependency injection setup, async patterns, and initial service implementations."
   - Output: C# implementations, interfaces, dependency configuration

### Phase 3: Quality & DevOps

5. **Developer Experience**
   - Use Task tool with subagent_type="dx-optimizer"
   - Prompt: "Optimize developer experience for the .NET solution. Create Makefile/scripts for common tasks (build, test, run), configure IDE settings (.vscode/settings.json), and add pre-commit hooks."
   - Output: Build scripts, IDE configurations, developer documentation

6. **Test Automation**
   - Use Task tool with subagent_type="test-automator"
   - Prompt: "Set up comprehensive testing for the .NET solution. Configure xUnit/NUnit, create initial test projects, and implement sample tests for the core implementations."
   - Output: Test project structure, sample tests, test configuration

7. **CI/CD Pipeline**
   - Use Task tool with subagent_type="deployment-engineer"
   - Prompt: "Create CI/CD pipeline for the .NET solution. Include GitHub Actions/Azure DevOps configuration for build, test, and deployment. Add containerization if applicable."
   - Output: Pipeline configuration, Dockerfile (if needed), deployment scripts

## For EXISTING Repository Fixes

### Phase 1: Comprehensive Audit

1. **Architecture Review**
   - Use Task tool with subagent_type="architect-review"
   - Prompt: "Review the .NET repository architecture for: $ARGUMENTS. Assess project structure, dependency management, and architectural patterns."
   - Output: Architecture assessment, improvement recommendations

2. **Code Quality Review**
   - Use Task tool with subagent_type="csharp-pro"
   - Prompt: "Review C# code quality in: $ARGUMENTS. Check for modern C# usage, async patterns, LINQ optimization, and dependency injection practices."
   - Output: Code quality report, refactoring suggestions

3. **Security Audit**
   - Use Task tool with subagent_type="security-auditor"
   - Prompt: "Audit .NET application security for: $ARGUMENTS. Check for OWASP vulnerabilities, authentication issues, and secure coding practices."
   - Output: Security findings, remediation steps

### Phase 2: Remediation

4. **Performance Analysis**
   - Use Task tool with subagent_type="performance-engineer"
   - Prompt: "Analyze performance bottlenecks in: $ARGUMENTS. Focus on async usage, database queries, memory allocation, and API response times."
   - Output: Performance report, optimization recommendations

5. **Test Coverage Analysis**
   - Use Task tool with subagent_type="test-automator"
   - Prompt: "Analyze test coverage and quality for: $ARGUMENTS. Identify gaps in unit, integration, and e2e testing."
   - Output: Coverage report, test improvement plan

6. **DevOps Review**
   - Use Task tool with subagent_type="devops-troubleshooter"
   - Prompt: "Review CI/CD and deployment practices for: $ARGUMENTS. Check pipeline efficiency, deployment strategies, and monitoring setup."
   - Output: DevOps assessment, pipeline improvements

### Phase 3: Implementation Plan

7. **Consolidated Report**
   - Aggregate all findings from previous agents
   - Categorize by severity: Critical, High, Medium, Low
   - Create prioritized implementation roadmap

8. **Generate Fixes**
   - Use Task tool with subagent_type="csharp-pro"
   - Prompt: "Generate code fixes for the critical and high-priority issues identified in: $ARGUMENTS. Provide modernized C# code following best practices."
   - Output: Pull request with fixes, migration guide

## Coordination Notes
- Each agent builds on outputs from previous agents
- Maintain context across all phases
- Ensure consistent .NET version targeting
- Document all breaking changes
- Provide rollback strategies for major changes

Repository details: $ARGUMENTS