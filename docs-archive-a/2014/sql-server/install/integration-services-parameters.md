---
title: Parâmetros de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, parameters
ms.assetid: b1bb3ea3-8097-4e76-b9c2-78a0f46a23bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 76a5ebe7018fdc58f02a4d2454d40f172c752c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685009"
---
# <a name="integration-services-parameters"></a><span data-ttu-id="495e0-102">Parâmetros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="495e0-102">Integration Services Parameters</span></span>
  <span data-ttu-id="495e0-103">Para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , você pode optar por analisar [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] os pacotes no computador ou os [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] arquivos de pacote no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="495e0-103">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you can decide to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer, or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package files in the file system.</span></span> <span data-ttu-id="495e0-104">Se você analisar arquivos no sistema de arquivos, forneça um caminho para a pasta que contém os pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="495e0-104">If you analyze files in the file system, provide a path to the folder that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="495e0-105">Opções</span><span class="sxs-lookup"><span data-stu-id="495e0-105">Options</span></span>  
 <span data-ttu-id="495e0-106">**Analisar pacotes SSIS no computador**</span><span class="sxs-lookup"><span data-stu-id="495e0-106">**Analyze SSIS packages on Computer**</span></span>  
 <span data-ttu-id="495e0-107">Selecione esta opção para analisar pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no computador.</span><span class="sxs-lookup"><span data-stu-id="495e0-107">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer.</span></span> <span data-ttu-id="495e0-108">Por padrão, essa opção é selecionada.</span><span class="sxs-lookup"><span data-stu-id="495e0-108">By default, this option is selected.</span></span>  
  
 <span data-ttu-id="495e0-109">**Analisar arquivos de pacote SSIS**</span><span class="sxs-lookup"><span data-stu-id="495e0-109">**Analyze SSIS package files**</span></span>  
 <span data-ttu-id="495e0-110">Selecione esta opção para analisar pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="495e0-110">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages in the file system.</span></span>  
  
 <span data-ttu-id="495e0-111">**Caminho para pacotes SSIS**</span><span class="sxs-lookup"><span data-stu-id="495e0-111">**Path to SSIS packages**</span></span>  
 <span data-ttu-id="495e0-112">Localize um UNC ou caminho local para seus pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="495e0-112">Locate a UNC or local path that holds your [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="495e0-113">Você não tem que incluir nomes de arquivos.</span><span class="sxs-lookup"><span data-stu-id="495e0-113">You do not have to include file names.</span></span> <span data-ttu-id="495e0-114">Se o caminho inserido não puder ser acessado, você não poderá clicar em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="495e0-114">If the path you have entered cannot be accessed, you cannot click **Next**.</span></span> <span data-ttu-id="495e0-115">Por padrão, o caminho fica em branco.</span><span class="sxs-lookup"><span data-stu-id="495e0-115">By default, the path is blank.</span></span> <span data-ttu-id="495e0-116">Esse campo é habilitado somente quando você seleciona **analisar arquivos de pacote SSIS**.</span><span class="sxs-lookup"><span data-stu-id="495e0-116">This field is enabled only when you select **Analyze SSIS package files**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="495e0-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="495e0-117">See Also</span></span>  
 <span data-ttu-id="495e0-118">[Trabalhando com o supervisor de atualização](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="495e0-118">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="495e0-119">Referência da interface de usuário do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="495e0-119">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
