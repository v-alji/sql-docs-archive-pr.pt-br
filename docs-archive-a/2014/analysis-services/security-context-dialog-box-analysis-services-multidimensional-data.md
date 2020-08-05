---
title: Caixa de diálogo contexto de segurança (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.securitycontext.f1
ms.assetid: 238a4a4b-84bd-4b3d-9f02-f3adf57fa3af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58d5f71172ac16087ecc342342e70ade234226a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570909"
---
# <a name="security-context-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="445de-102">Caixa de diálogo Contexto de Segurança (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="445de-102">Security Context Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="445de-103">Use a caixa de diálogo **Contexto de Segurança** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para alterar o usuário e a função usados para examinar dados ou metadados para um objeto do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="445de-103">Use the **Security Context** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to change the user and role used to examine data or metadata for a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="445de-104">É possível exibir a caixa de diálogo **Contexto de Segurança** clicando em **Contexto de Segurança** no painel **Barra de Ferramentas** na guia **Cálculos** ou na guia **Navegador** no Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="445de-104">You can display the **Security Context** dialog box by clicking **Security Context** in the **Toolbar** pane on either the **Calculations** tab or the **Browser** tab in Cube Designer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="445de-105">Opções</span><span class="sxs-lookup"><span data-stu-id="445de-105">Options</span></span>  
 <span data-ttu-id="445de-106">**Usuário atual**</span><span class="sxs-lookup"><span data-stu-id="445de-106">**Current user**</span></span>  
 <span data-ttu-id="445de-107">Selecione para usar o domínio e o nome do usuário atuais ao exibir os dados e metadados do objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="445de-107">Select to use the domain and user name of the current user while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="445de-108">**Outro usuário**</span><span class="sxs-lookup"><span data-stu-id="445de-108">**Other user**</span></span>  
 <span data-ttu-id="445de-109">Digite o domínio e o nome de outro usuário ou grupo a serem usados ao exibir os dados e metadados do objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="445de-109">Type the domain and user name of another user or group to use while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="445de-110">O domínio e o nome de usuário ou grupo usam o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="445de-110">The domain and name of the user or group uses the following format:</span></span>  
  
 <span data-ttu-id="445de-111">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="445de-111">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="445de-112">**Funções**</span><span class="sxs-lookup"><span data-stu-id="445de-112">**Roles**</span></span>  
 <span data-ttu-id="445de-113">Selecione para usar uma ou mais funções especificadas ao exibir os dados e metadados do objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="445de-113">Select to use one or more specified roles when viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="445de-114">Você poderá selecionar as funções para uso, se várias funções estiverem definidas no banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="445de-114">You can select the roles to use if multiple roles are defined in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="445de-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="445de-115">See Also</span></span>  
 <span data-ttu-id="445de-116">[KPIs &#40;designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="445de-116">[KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="445de-117">[Navegador &#40;designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="445de-117">[Browser &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="445de-118">Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="445de-118">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
