---
title: Caixa de diálogo Avaliar Políticas, página Seleção de Políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.runnow.f1
ms.assetid: 20075fbe-0b48-42c8-b747-690f1aa23dcf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f68a1ccc7873b6a05d2641ddaa87e8d5b0e5c6d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679295"
---
# <a name="evaluate-policies-dialog-box-policy-selection-page"></a><span data-ttu-id="5c01b-102">Caixa de diálogo Avaliar Políticas, página Seleção de Políticas</span><span class="sxs-lookup"><span data-stu-id="5c01b-102">Evaluate Policies Dialog Box, Policy Selection Page</span></span>
  <span data-ttu-id="5c01b-103">Use esta caixa de diálogo para avaliar políticas do Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="5c01b-103">Use this dialog box to evaluate Policy-Based Management policies.</span></span> <span data-ttu-id="5c01b-104">Ao selecionar a página **Resultados da Avaliação** , você pode aplicar políticas aos itens em um conjunto de destino que não esteja em conformidade com as políticas.</span><span class="sxs-lookup"><span data-stu-id="5c01b-104">By selecting the **Evaluation Results** page, you can apply policies to the items in a target set that do not comply with the policies.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5c01b-105">Opções</span><span class="sxs-lookup"><span data-stu-id="5c01b-105">Options</span></span>  
 <span data-ttu-id="5c01b-106">**Origem**</span><span class="sxs-lookup"><span data-stu-id="5c01b-106">**Source**</span></span>  
 <span data-ttu-id="5c01b-107">Especifica a origem das políticas.</span><span class="sxs-lookup"><span data-stu-id="5c01b-107">Specifies the source of the policies.</span></span> <span data-ttu-id="5c01b-108">Para alterar a origem, clique no botão Procurar (**...**) para abrir a caixa de diálogo **Selecionar Origem** .</span><span class="sxs-lookup"><span data-stu-id="5c01b-108">To change the source, click the Browse (**...**) button to open the **Select Source** dialog box.</span></span>  
  
 <span data-ttu-id="5c01b-109">**Arquivos**</span><span class="sxs-lookup"><span data-stu-id="5c01b-109">**Files**</span></span>  
 <span data-ttu-id="5c01b-110">Digite o caminho de um arquivo que contenha uma política de Gerenciamento Baseado em Políticas ou use o botão Procurar (**...**) para selecionar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="5c01b-110">Type the path of a file that contains a Policy-Based Management policy, or use the Browse (**...**) button to select the file.</span></span>  
  
 <span data-ttu-id="5c01b-111">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="5c01b-111">**Server**</span></span>  
 <span data-ttu-id="5c01b-112">Selecione para conectar-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que contenha a política desejada.</span><span class="sxs-lookup"><span data-stu-id="5c01b-112">Select to connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that contains the policy that you want.</span></span>  
  
 <span data-ttu-id="5c01b-113">**Políticas: Política**</span><span class="sxs-lookup"><span data-stu-id="5c01b-113">**Policies: Policy**</span></span>  
 <span data-ttu-id="5c01b-114">Clique para abrir a caixa de diálogo da política especificada.</span><span class="sxs-lookup"><span data-stu-id="5c01b-114">Click to open the policy dialog box for the specified policy.</span></span>  
  
 <span data-ttu-id="5c01b-115">**Políticas: Categoria**</span><span class="sxs-lookup"><span data-stu-id="5c01b-115">**Policies: Category**</span></span>  
 <span data-ttu-id="5c01b-116">A categoria da política.</span><span class="sxs-lookup"><span data-stu-id="5c01b-116">The category of the policy.</span></span> <span data-ttu-id="5c01b-117">Essa caixa é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="5c01b-117">This box is read-only.</span></span>  
  
 <span data-ttu-id="5c01b-118">**Políticas: Faceta**</span><span class="sxs-lookup"><span data-stu-id="5c01b-118">**Policies: Facet**</span></span>  
 <span data-ttu-id="5c01b-119">A faceta implementada pela política.</span><span class="sxs-lookup"><span data-stu-id="5c01b-119">The facet implemented by the policy.</span></span> <span data-ttu-id="5c01b-120">Essa caixa é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="5c01b-120">This box is read-only.</span></span>  
  
 <span data-ttu-id="5c01b-121">**Avaliado**</span><span class="sxs-lookup"><span data-stu-id="5c01b-121">**Evaluate**</span></span>  
 <span data-ttu-id="5c01b-122">Executa a política no modo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="5c01b-122">Runs the policy in evaluation mode.</span></span> <span data-ttu-id="5c01b-123">Isso gera um relatório de conformidade para o conjunto de destino, mas não reconfigura o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nem impõe conformidade no futuro.</span><span class="sxs-lookup"><span data-stu-id="5c01b-123">This generates a compliance report for the target set but does not reconfigure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or enforce future compliance.</span></span>  
  
## <a name="possible-errors"></a><span data-ttu-id="5c01b-124">Possíveis erros</span><span class="sxs-lookup"><span data-stu-id="5c01b-124">Possible Errors</span></span>  
  
-   <span data-ttu-id="5c01b-125">**Nenhum destino encontrado**</span><span class="sxs-lookup"><span data-stu-id="5c01b-125">**No targets found**</span></span>  
  
     <span data-ttu-id="5c01b-126">O conjunto de destino pode estar vazio devido a qualquer um destes motivos:</span><span class="sxs-lookup"><span data-stu-id="5c01b-126">The target set could be empty due to any of the following reasons:</span></span>  
  
    -   <span data-ttu-id="5c01b-127">Na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , não há nenhum destino do tipo especificado pela política.</span><span class="sxs-lookup"><span data-stu-id="5c01b-127">There are no targets on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] of the type specified by the policy.</span></span>  
  
    -   <span data-ttu-id="5c01b-128">A restrição de servidor pode excluir a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contém o destino.</span><span class="sxs-lookup"><span data-stu-id="5c01b-128">The server restriction might exclude the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains the target.</span></span>  
  
    -   <span data-ttu-id="5c01b-129">Se a política estiver em um objeto de um banco de dados (por exemplo, uma tabela, exibição ou um usuário), o banco de dados não poderá assinar a categoria da política.</span><span class="sxs-lookup"><span data-stu-id="5c01b-129">If the policy is on an object in a database (for example a table, view, or user) the database might not subscribe to the category of the policy.</span></span>  
  
    -   <span data-ttu-id="5c01b-130">O filtro do conjunto de destino pode excluir todos os destinos dessa instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c01b-130">The target-set filter might exclude all targets on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="5c01b-131">O tipo de servidor de destino é diferente do tipo de servidor no qual a política é avaliada.</span><span class="sxs-lookup"><span data-stu-id="5c01b-131">The target server type is different from the server type on which the policy is evaluated.</span></span> <span data-ttu-id="5c01b-132">Por exemplo, no [!INCLUDE[ssDE](../../includes/ssde-md.md)], se você tentar avaliar uma política criada para o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], receberá um conjunto de destino vazio.</span><span class="sxs-lookup"><span data-stu-id="5c01b-132">For example, in the [!INCLUDE[ssDE](../../includes/ssde-md.md)], if you try to evaluate a policy that has been created for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you will receive an empty target set</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c01b-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5c01b-133">See Also</span></span>  
 <span data-ttu-id="5c01b-134">[Administrar servidores usando o gerenciamento baseado em políticas](administer-servers-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="5c01b-134">[Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md) </span></span>  
 [<span data-ttu-id="5c01b-135">Caixa de diálogo Avaliar Políticas, página Resultados da Avaliação</span><span class="sxs-lookup"><span data-stu-id="5c01b-135">Evaluate Policies Dialog Box, Evaluation Results Page</span></span>](evaluate-policies-dialog-box-evaluation-results-page.md)  
  
  
