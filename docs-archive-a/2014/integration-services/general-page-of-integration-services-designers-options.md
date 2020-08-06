---
title: Página geral | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Business_Intelligence_Designers.Data_Transformation_Designers.General
ms.assetid: d695690a-923b-4036-945e-7621e8651deb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59073ac29f95f1e64bd0a9382366e9539ce1408a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570138"
---
# <a name="general-page"></a><span data-ttu-id="b9ca6-102">Página Geral</span><span class="sxs-lookup"><span data-stu-id="b9ca6-102">General Page</span></span>
  <span data-ttu-id="b9ca6-103">Use a página **Geral** da página **Designers do Integration Services** na caixa de diálogo **Opções** para especificar as opções de carregamento, exibição e atualização de pacotes.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-103">Use the **General** page of the **Integration Services Designers** page in the **Options** dialog box to specify the options for loading, displaying, and upgrading packages.</span></span>  
  
 <span data-ttu-id="b9ca6-104">Para abrir a página **Geral** , em [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], no menu **Ferramentas** , clique em **Opções**, expanda **Designers do Business Intelligence**e selecione **Designers do Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-104">To open the **General** page, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Tools** menu, click **Options**, expand **Business Intelligence Designers**, and select **Integration Services Designers**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b9ca6-105">Opções</span><span class="sxs-lookup"><span data-stu-id="b9ca6-105">Options</span></span>  
 <span data-ttu-id="b9ca6-106">**Verificar assinatura digital ao carregar um pacote**</span><span class="sxs-lookup"><span data-stu-id="b9ca6-106">**Check digital signature when loading a package**</span></span>  
 <span data-ttu-id="b9ca6-107">Selecione para que o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] verifique a assinatura digital ao carregar um pacote.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-107">Select to have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] check the digital signature when loading a package.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="b9ca6-108">apenas verificará se a assinatura digital está presente, é válida e é de uma fonte confiável.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-108">will only check whether the digital signature is present, is valid, and is from a trusted source.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="b9ca6-109">não verificará se o pacote foi alterado depois que o pacote for assinado.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-109">will not check whether the package has been changed since the package was signed.</span></span>  
  
 <span data-ttu-id="b9ca6-110">Se você definir o valor de registro **BlockedSignatureStates** , esse valor de registro substituirá a opção **Verificar assinatura digital ao carregar um pacote** .</span><span class="sxs-lookup"><span data-stu-id="b9ca6-110">If you set the **BlockedSignatureStates** registry value, this registry value overrides the **Check digital signature when loading a package** option.</span></span> <span data-ttu-id="b9ca6-111">Para obter mais informações, consulte [Como implementar uma política de assinatura definindo um valor do Registro](implement-a-signing-policy-by-setting-a-registry-value.md).</span><span class="sxs-lookup"><span data-stu-id="b9ca6-111">For more information, see [Implement a Signing Policy by Setting a Registry Value](implement-a-signing-policy-by-setting-a-registry-value.md).</span></span>  
  
 <span data-ttu-id="b9ca6-112">Para obter mais informações sobre certificados e pacotes digitais, consulte [Identificar a origem de pacotes com assinaturas digitais](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="b9ca6-112">For more information about digital certificates and packages, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
 <span data-ttu-id="b9ca6-113">**Mostrar aviso se o pacote não estiver assinado**</span><span class="sxs-lookup"><span data-stu-id="b9ca6-113">**Show warning if package is unsigned**</span></span>  
 <span data-ttu-id="b9ca6-114">Selecione para exibir um aviso ao carregar um pacote que não está assinado.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-114">Select to display a warning when loading a package that is not signed.</span></span>  
  
 <span data-ttu-id="b9ca6-115">**Mostrar rótulos de restrição de precedência**</span><span class="sxs-lookup"><span data-stu-id="b9ca6-115">**Show precedence constraint labels**</span></span>  
 <span data-ttu-id="b9ca6-116">Selecione qual rótulo – Êxito, Falha ou Conclusão – será exibido em restrições de precedência ao exibir pacotes em [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9ca6-116">Select which label-Success, Failure, or Completion-to display on precedence constraints when viewing packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="b9ca6-117">**Idioma do script**</span><span class="sxs-lookup"><span data-stu-id="b9ca6-117">**Scripting language**</span></span>  
 <span data-ttu-id="b9ca6-118">Selecione o idioma padrão de scripts para novas tarefas e componentes de Script.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-118">Select the default scripting language for new Script tasks and Script components.</span></span>  
  
 <span data-ttu-id="b9ca6-119">**Atualizar cadeias de conexão para usar novos nomes de provedor**</span><span class="sxs-lookup"><span data-stu-id="b9ca6-119">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="b9ca6-120">Ao abrir ou atualizar pacotes do [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] , atualize as cadeias de conexão para usar os nomes dos seguintes provedores, para a versão atual do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b9ca6-120">When opening or upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, update connection strings to use the names for the following providers, for the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="b9ca6-121">Provedor OLE DB</span><span class="sxs-lookup"><span data-stu-id="b9ca6-121">OLE DB provider</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="b9ca6-122">Native Client</span><span class="sxs-lookup"><span data-stu-id="b9ca6-122">Native Client</span></span>  
  
 <span data-ttu-id="b9ca6-123">O Assistente de Atualização de Pacotes [!INCLUDE[ssIS](../includes/ssis-md.md)] só atualiza cadeias de conexão armazenadas em gerenciadores de conexões.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-123">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="b9ca6-124">O assistente não atualiza cadeias de conexão construídas dinamicamente com a linguagem de expressão do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou o código de uma tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-124">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="b9ca6-125">**Criar nova ID de pacote**</span><span class="sxs-lookup"><span data-stu-id="b9ca6-125">**Create new package ID**</span></span>  
 <span data-ttu-id="b9ca6-126">Ao atualizar os pacotes de [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] , crie novas IDs de pacote para as versões atualizadas dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-126">When upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, create new package IDs for the upgraded versions of the packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ca6-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b9ca6-127">See Also</span></span>  
 <span data-ttu-id="b9ca6-128">[Visão geral de segurança &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="b9ca6-128">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="b9ca6-129">Estender pacotes com scripts</span><span class="sxs-lookup"><span data-stu-id="b9ca6-129">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
  
  
