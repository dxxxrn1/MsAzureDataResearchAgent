# Troubleshooting Log

## Issue: Azure OpenAI Quota Limitations & VS Code Extension Sync

### Problem Encountered
- **Date:** December 18, 2025
- **Issue 1:** Unable to deploy GPT-4o, GPT-4o-mini, or GPT-3.5-turbo models through VS Code
- **Error:** "Insufficient quota available"
- **Issue 2:** VS Code extension not syncing with projects created in Azure portal
- **Tried:** Multiple regions, multiple projects, different deployment types

### Root Causes Identified

#### 1. Azure OpenAI Quota Limitations
Azure trial subscriptions have strict quota limits on Azure OpenAI services limiting 
- Number of concurrent model deployments
- Tokens per minute capacity
- Regional availability
- Deployment type options

#### 2. VS Code Extension Synchronization Issues
The Microsoft Foundry VS Code extension experienced sync problems:
- Projects created in Azure portal not properly recognized in VS Code
- Deployed models not appearing after refresh
- Extension attempting to create new projects instead of connecting to existing ones

### Resolution Attempts

**Quota Issues:**
1. ✗ Tried different deployment types (Global Provisioned Throughput, Standard)
2. ✗ Tried smaller models (gpt-4o-mini)
3. ✗ Created multiple projects in different regions (West US 2, East US 2)
4. ✓ **SUCCESS:** Deployed model through Azure AI Studio portal (ai.azure.com)

**VS Code Sync Issues:**
1. ✗ Refreshed Resources view multiple times
2. ✗ Signed out and back in to VS Code extension
3. ✗ Reloaded VS Code window
4. ✓ **WORKAROUND:** Deleted all previous projects, created fresh project in portal
5. ✓ **SUCCESS:** New project and deployed model now visible in VS Code

### Final Working Configuration
- **Project:** AiAgentprjct
- **Region:** EastUS
- **Model:** gpt-4o-mini

### Lessons Learned

1. **Quota Management:**
   - Trial accounts have restrictive AI service quotas separate from billing credits
   - Regional quota availability varies significantly
   - Production workloads require quota increase requests submitted through Azure portal

2. **Tool Limitations:**
   - VS Code extensions in preview may have sync issues
   - Azure portal deployment is more reliable for initial setup
   - Hybrid approach (portal + VS Code) can be necessary
   - Multiple tool interfaces provide flexibility when one fails

3. **Troubleshooting Approach:**
   - Start fresh when debugging complex sync issues
   - Clean slate approach (delete all, recreate) can resolve persistent problems
   - Use portal as source of truth for resource verification
   - Document errors and attempts for future reference

4. **Cost Awareness:**
   - Monitor credit usage regularly during learning
   - Delete resources immediately after exercises
   - Consider model size and deployment type impact on quota
   - Plan exercises based on remaining credits

### Best Practices Established
- ✅ Deploy models through Azure AI Studio portal first
- ✅ Verify deployment in portal before checking VS Code
- ✅ Use minimal quota settings (lowest tokens per minute)
- ✅ Delete old projects before creating new ones
- ✅ Document all resource names and regions for tracking
- ✅ Regular resource cleanup to free quota
- ✅ Keep troubleshooting logs for portfolio documentation
,
