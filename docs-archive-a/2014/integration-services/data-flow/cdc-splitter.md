---
title: Divisor de CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsplitter.f1
ms.assetid: 167bc5c6-fa36-439d-987c-b20acd1a77e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45dd16602625b28d2ca7e16f2fa6b0d62294fe81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575249"
---
# <a name="cdc-splitter"></a><span data-ttu-id="b664c-102">Separador de CDC</span><span class="sxs-lookup"><span data-stu-id="b664c-102">CDC Splitter</span></span>
  <span data-ttu-id="b664c-103">O separador de CDC divide um único fluxo de linhas de alteração de um fluxo de dados de origem CDC em diferentes fluxos de dados para operações de Inserir, Atualizar e Excluir.</span><span class="sxs-lookup"><span data-stu-id="b664c-103">The CDC splitter splits a single flow of change rows from a CDC source data flow into different data flows for Insert, Update and Delete operations.</span></span> <span data-ttu-id="b664c-104">O fluxo de dados é dividido com base na coluna necessária de `__$operation` e seus valores padrão em tabelas de alterações do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b664c-104">The data flow is split based on the required column `__$operation` and its standard values in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables.</span></span>  
  
|<span data-ttu-id="b664c-105">Valor da operação</span><span class="sxs-lookup"><span data-stu-id="b664c-105">Value of Operation</span></span>|<span data-ttu-id="b664c-106">Saída</span><span class="sxs-lookup"><span data-stu-id="b664c-106">Output</span></span>|<span data-ttu-id="b664c-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b664c-107">Description</span></span>|  
|------------------------|------------|-----------------|  
|<span data-ttu-id="b664c-108">1</span><span class="sxs-lookup"><span data-stu-id="b664c-108">1</span></span>|<span data-ttu-id="b664c-109">Excluir</span><span class="sxs-lookup"><span data-stu-id="b664c-109">Delete</span></span>|<span data-ttu-id="b664c-110">Linha excluída</span><span class="sxs-lookup"><span data-stu-id="b664c-110">Deleted Row</span></span>|  
|<span data-ttu-id="b664c-111">2</span><span class="sxs-lookup"><span data-stu-id="b664c-111">2</span></span>|<span data-ttu-id="b664c-112">Insert</span><span class="sxs-lookup"><span data-stu-id="b664c-112">Insert</span></span>|<span data-ttu-id="b664c-113">Linha inserida (não disponível durante o uso do modo de CDC **Rede com Mesclagem** )</span><span class="sxs-lookup"><span data-stu-id="b664c-113">Inserted row (not available when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="b664c-114">3</span><span class="sxs-lookup"><span data-stu-id="b664c-114">3</span></span>|<span data-ttu-id="b664c-115">Atualizar</span><span class="sxs-lookup"><span data-stu-id="b664c-115">Update</span></span>|<span data-ttu-id="b664c-116">Linha Before-update (disponível apenas durante o uso do modo de CDC **Tudo com Valores Antigos** )</span><span class="sxs-lookup"><span data-stu-id="b664c-116">Before-update row (available only when using **All with Old Values** CDC mode)</span></span>|  
|<span data-ttu-id="b664c-117">4</span><span class="sxs-lookup"><span data-stu-id="b664c-117">4</span></span>|<span data-ttu-id="b664c-118">Atualizar</span><span class="sxs-lookup"><span data-stu-id="b664c-118">Update</span></span>|<span data-ttu-id="b664c-119">Linha After-update (após Before-update)</span><span class="sxs-lookup"><span data-stu-id="b664c-119">After-update row (follows the Before-update)</span></span>|  
|<span data-ttu-id="b664c-120">5</span><span class="sxs-lookup"><span data-stu-id="b664c-120">5</span></span>|<span data-ttu-id="b664c-121">Atualizar</span><span class="sxs-lookup"><span data-stu-id="b664c-121">Update</span></span>|<span data-ttu-id="b664c-122">Linha Merge (disponível apenas durante o uso do modo CDC **Rede com Mesclagem** )</span><span class="sxs-lookup"><span data-stu-id="b664c-122">Merge row (available only when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="b664c-123">Outros</span><span class="sxs-lookup"><span data-stu-id="b664c-123">Other</span></span>|<span data-ttu-id="b664c-124">Erro</span><span class="sxs-lookup"><span data-stu-id="b664c-124">Error</span></span>||  
  
 <span data-ttu-id="b664c-125">Você pode usar o separador para se conectar a saídas INSERT, DELETE e UPDATE predefinidas para processamento adicional.</span><span class="sxs-lookup"><span data-stu-id="b664c-125">You can use the splitter to connect to pre-defined INSERT, DELETE, and UPDATE outputs for further processing.</span></span>  
  
 <span data-ttu-id="b664c-126">A transformação de Separador de CDC tem uma entrada e uma saída comum.</span><span class="sxs-lookup"><span data-stu-id="b664c-126">The CDC Splitter transformation has one regular input and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="b664c-127">Tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="b664c-127">Error Handling</span></span>  
 <span data-ttu-id="b664c-128">A transformação do Separador de CDC tem uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="b664c-128">The CDC Splitter transformation has an error output.</span></span> <span data-ttu-id="b664c-129">As linhas Input com um valor inválido da coluna $operation são consideradas errôneas e são tratadas de acordo com a propriedade **ErrorRowDisposition** da entrada.</span><span class="sxs-lookup"><span data-stu-id="b664c-129">Input rows with an invalid value of the $operation column are considered erroneous and are handled according to the **ErrorRowDisposition** property of the input.</span></span>  
  
 <span data-ttu-id="b664c-130">A saída de erro de componente inclui as colunas de saída seguintes:</span><span class="sxs-lookup"><span data-stu-id="b664c-130">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="b664c-131">**Código de Erro**: definida como 1.</span><span class="sxs-lookup"><span data-stu-id="b664c-131">**Error Code**: Set to 1.</span></span>  
  
-   <span data-ttu-id="b664c-132">**Coluna de Erro**: a coluna de origem que causa o erro (para erros de conversão).</span><span class="sxs-lookup"><span data-stu-id="b664c-132">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="b664c-133">**Colunas de Linha de erro**: as colunas de entrada da linha que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="b664c-133">**Error Row Columns**: The input columns of the row that caused the error.</span></span>  
  
## <a name="configuring-the-cdc-splitter"></a><span data-ttu-id="b664c-134">Configurando o Separador de CDC</span><span class="sxs-lookup"><span data-stu-id="b664c-134">Configuring the CDC Splitter</span></span>  
 <span data-ttu-id="b664c-135">Não há nenhuma propriedade configurável para o separador de CDC.</span><span class="sxs-lookup"><span data-stu-id="b664c-135">There are no configurable properties for the CDC splitter.</span></span>  
  
 <span data-ttu-id="b664c-136">Para obter mais informações sobre como usar o separador de CDC, consulte Componentes de CDC para Microsoft SQL Server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="b664c-136">For more information about using the CDC splitter, see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
 <span data-ttu-id="b664c-137">A caixa de diálogo **Editor Avançado** contém as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="b664c-137">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="b664c-138">Para abrir a caixa de diálogo **Editor Avançado** :</span><span class="sxs-lookup"><span data-stu-id="b664c-138">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="b664c-139">Na tela **Fluxo de Dados** do seu projeto do [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , clique com o botão direito do mouse no separador de CDC e selecione **Mostrar Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="b664c-139">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b664c-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b664c-140">See Also</span></span>  
 [<span data-ttu-id="b664c-141">Direcionar o fluxo de CDC de acordo com o tipo de alteração</span><span class="sxs-lookup"><span data-stu-id="b664c-141">Direct the CDC Stream According to the Type of Change</span></span>](direct-the-cdc-stream-according-to-the-type-of-change.md)  
  
  
