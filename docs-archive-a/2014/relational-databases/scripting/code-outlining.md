---
title: Estruturação do código
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], outlining code
- Query Editor [SQL Server Management Studio], hiding code
ms.assetid: 556c7dfe-7bc8-4cab-a36f-2b753a05d3f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 0a142ca8fbdcdfcfbfd1b71de06c0b0fd4c5339c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572460"
---
# <a name="code-outlining"></a><span data-ttu-id="56f68-102">Estruturação do código</span><span class="sxs-lookup"><span data-stu-id="56f68-102">Code Outlining</span></span>
  <span data-ttu-id="56f68-103">Você pode usar o recurso de estrutura de tópicos nos editores de consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] para ocultar código, de forma seletiva, ao editar consultas.</span><span class="sxs-lookup"><span data-stu-id="56f68-103">You can use the outlining feature in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] query editors to selectively hide code when you edit queries.</span></span> <span data-ttu-id="56f68-104">Isso permite exibir com mais facilidade o código em que você está trabalhando, principalmente em arquivos de consulta grandes.</span><span class="sxs-lookup"><span data-stu-id="56f68-104">This enables you to more easily view the code you are working on, especially in large query files.</span></span>

## <a name="outlining-overview"></a><span data-ttu-id="56f68-105">Visão geral da estrutura de tópicos</span><span class="sxs-lookup"><span data-stu-id="56f68-105">Outlining Overview</span></span>
 <span data-ttu-id="56f68-106">Por padrão, todo o código é visível quando você abre uma janela do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="56f68-106">By default, all code is visible when you open a query editor window.</span></span> <span data-ttu-id="56f68-107">Regiões do código podem ser recolhidas para não serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="56f68-107">Regions of the code can be collapsed to hide it from view.</span></span> <span data-ttu-id="56f68-108">Na extremidade esquerda da janela do editor há uma linha vertical onde um quadrado com um sinal de menos (-) serve para identificar o início de cada região de código que pode ser recolhida.</span><span class="sxs-lookup"><span data-stu-id="56f68-108">A vertical line on the left edge of the editor window uses a square with a minus sign (-) to identify the start of each collapsible code region.</span></span> <span data-ttu-id="56f68-109">Quando você clica em um sinal de menos, o texto da região de código é substituído por uma caixa com três pontos (…) e o sinal de menos muda para um sinal de mais (+).</span><span class="sxs-lookup"><span data-stu-id="56f68-109">When you click a minus sign, the text of the code region is replaced with a box that contains three periods (...), and the minus sign changes to a plus sign (+).</span></span> <span data-ttu-id="56f68-110">Quando você clica em um sinal de mais, o código recolhido é exibido e o sinal de mais muda para um sinal de menos.</span><span class="sxs-lookup"><span data-stu-id="56f68-110">When you click a plus sign, the collapsed code appears and the plus sign changes to a minus sign.</span></span> <span data-ttu-id="56f68-111">Quando você move o ponteiro sobre uma caixa com três pontos, uma dica de ferramenta é exibida com o código da seção recolhida.</span><span class="sxs-lookup"><span data-stu-id="56f68-111">When you move the pointer over a box that has three periods, a tooltip appears that shows the code in the collapsed section.</span></span>

## <a name="system-outline-regions"></a><span data-ttu-id="56f68-112">Regiões de estrutura de tópicos do sistema</span><span class="sxs-lookup"><span data-stu-id="56f68-112">System Outline Regions</span></span>
 <span data-ttu-id="56f68-113">Cada editor do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] gera um conjunto de regiões de estrutura de tópicos padrão definidas pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="56f68-113">Each [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] editor generates a set of default, system-defined outline regions.</span></span>

 <span data-ttu-id="56f68-114">Os editores de códigos MDX e DMX criam regiões de estrutura de tópicos para cada instrução multilinha.</span><span class="sxs-lookup"><span data-stu-id="56f68-114">The MDX and DMX code editors create outline regions for each multiline statement.</span></span> <span data-ttu-id="56f68-115">Esse é o único nível de estrutura de tópicos que tem o suporte desses editores.</span><span class="sxs-lookup"><span data-stu-id="56f68-115">This is the only level of outlining that these editors support.</span></span>

### <a name="analysis-services-xmla-query-editor-regions"></a><span data-ttu-id="56f68-116">Regiões do Editor de Consultas XMLA do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="56f68-116">Analysis Services XMLA Query Editor Regions</span></span>
 <span data-ttu-id="56f68-117">O Editor de Consultas XMLA do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gera uma região de estrutura de tópicos para cada atributo XML multilinha.</span><span class="sxs-lookup"><span data-stu-id="56f68-117">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query Editor generates an outline region for each multiline XML attribute.</span></span> <span data-ttu-id="56f68-118">O editor aninha essas regiões para marcas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="56f68-118">The editor nests the outline regions for nested tags.</span></span> <span data-ttu-id="56f68-119">Por exemplo, o Editor XMLA cria três regiões de estrutura de tópicos para o documento seguinte.</span><span class="sxs-lookup"><span data-stu-id="56f68-119">For example, the XMLA Editor creates three outline regions for the following document.</span></span>

 <span data-ttu-id="56f68-120">![Código XML que mostra a estrutura de tópicos](../../database-engine/media/editoutlinexmlfull.gif "Código XML que mostra a estrutura de tópicos")</span><span class="sxs-lookup"><span data-stu-id="56f68-120">![XML code showing outlining](../../database-engine/media/editoutlinexmlfull.gif "XML code showing outlining")</span></span>

 <span data-ttu-id="56f68-121">Quando você clica no sinal de menos na \<InnerTag> linha, apenas o InnerTag é recolhido, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="56f68-121">When you click the minus sign on the \<InnerTag> line, just the InnerTag is collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="56f68-122">![Código XML com nó interno oculto](../../database-engine/media/editoutlinexmlinnercol.gif "Código XML com nó interno oculto")</span><span class="sxs-lookup"><span data-stu-id="56f68-122">![XML code with inner node hidden](../../database-engine/media/editoutlinexmlinnercol.gif "XML code with inner node hidden")</span></span>

 <span data-ttu-id="56f68-123">Quando você move o ponteiro sobre a caixa com os três pontos, o código da região recolhida é exibido em uma dica de ferramenta, como mostra a ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="56f68-123">When you move the pointer over the box that has the three periods (...), the code in the collapsed region appears in a tooltip, as shown in the following illustration.</span></span>

 <span data-ttu-id="56f68-124">![Código XML com dica de ferramenta que mostra código oculto](../../database-engine/media/editoutlinexmlmouse.gif "Código XML com dica de ferramenta que mostra código oculto")</span><span class="sxs-lookup"><span data-stu-id="56f68-124">![XML code with tooltip showing hidden code](../../database-engine/media/editoutlinexmlmouse.gif "XML code with tooltip showing hidden code")</span></span>

 <span data-ttu-id="56f68-125">Quando você clica no sinal de menos na \<MiddleTag> linha, MiddleTag e InnerTag são recolhidos, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="56f68-125">When you click the minus sign on the \<MiddleTag> line, both the MiddleTag and InnerTag are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="56f68-126">![Código XML com as marcas interna e central ocultas](../../database-engine/media/editoutlinexmlmiddlecol.gif "Código XML com as marcas interna e central ocultas")</span><span class="sxs-lookup"><span data-stu-id="56f68-126">![XML code with inner and middle tags hidden](../../database-engine/media/editoutlinexmlmiddlecol.gif "XML code with inner and middle tags hidden")</span></span>

 <span data-ttu-id="56f68-127">Quando você clica no sinal de menos na \<OuterTag> linha, todas as três linhas são recolhidas, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="56f68-127">When you click the minus sign on the \<OuterTag> line, all three lines are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="56f68-128">![Código XML que mostra todas as três marcas ocultas](../../database-engine/media/editoutlinexmloutercol.gif "Código XML que mostra todas as três marcas ocultas")</span><span class="sxs-lookup"><span data-stu-id="56f68-128">![XML code showing all three tags hidden](../../database-engine/media/editoutlinexmloutercol.gif "XML code showing all three tags hidden")</span></span>

### <a name="database-engine-query-editor-regions"></a><span data-ttu-id="56f68-129">Regiões do Editor de Consultas do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="56f68-129">Database Engine Query Editor Regions</span></span>
 <span data-ttu-id="56f68-130">O Editor de Consultas do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] gera regiões de estrutura de tópicos para cada elemento na seguinte hierarquia:</span><span class="sxs-lookup"><span data-stu-id="56f68-130">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor generates outline regions for each element in the following hierarchy:</span></span>

1.  <span data-ttu-id="56f68-131">Lotes.</span><span class="sxs-lookup"><span data-stu-id="56f68-131">Batches.</span></span> <span data-ttu-id="56f68-132">O primeiro lote é o código, do início do arquivo até o primeiro comando GO ou até o fim do arquivo, quando não há comandos GO.</span><span class="sxs-lookup"><span data-stu-id="56f68-132">The first batch is the code from the start of the file to either the first GO command or the end of the file when there are no GO commands.</span></span> <span data-ttu-id="56f68-133">Após o primeiro GO, há um lote de cada comando GO até o próximo comando GO, ou até o fim do arquivo.</span><span class="sxs-lookup"><span data-stu-id="56f68-133">After the first GO, there is one batch from each GO command to either the next GO command or the end of the file.</span></span>

2.  <span data-ttu-id="56f68-134">Blocos delimitados pelas seguintes palavras-chave:</span><span class="sxs-lookup"><span data-stu-id="56f68-134">Blocks delimited by the following keywords:</span></span>

    -   <span data-ttu-id="56f68-135">BEGIN - END</span><span class="sxs-lookup"><span data-stu-id="56f68-135">BEGIN - END</span></span>

    -   <span data-ttu-id="56f68-136">BEGIN TRY - END TRY</span><span class="sxs-lookup"><span data-stu-id="56f68-136">BEGIN TRY - END TRY</span></span>

    -   <span data-ttu-id="56f68-137">BEGIN CATCH - END CATCH</span><span class="sxs-lookup"><span data-stu-id="56f68-137">BEGIN CATCH - END CATCH</span></span>

3.  <span data-ttu-id="56f68-138">Instruções multilinha.</span><span class="sxs-lookup"><span data-stu-id="56f68-138">Multiline statements.</span></span>

 <span data-ttu-id="56f68-139">Por exemplo, o Editor de Consultas do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] cria três regiões de estrutura de tópicos para a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="56f68-139">For example, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor creates three outline regions for the following query:</span></span>

```
CREATE PROCEDURE Sales.SampleProc --Outline region 1
AS
BEGIN --Outline region 2 
  SELECT GETDATE() AS TimeOfQuery;
  SELECT * --Outline region 3
  FROM sys.transmission_queue;
  SELECT @@VERSION;
END;
GO
```

 <span data-ttu-id="56f68-140">Você pode clicar no sinal de menos na linha `SELECT *` para recolher somente essa instrução `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="56f68-140">You can click the minus sign on the `SELECT *` line to collapse just that `SELECT` statement.</span></span> <span data-ttu-id="56f68-141">Para recolher todo o bloco `BEGIN - END` , clique no sinal de menos na linha `BEGIN` .</span><span class="sxs-lookup"><span data-stu-id="56f68-141">To collapse the whole `BEGIN - END` block, click the minus sign on the `BEGIN` line.</span></span> <span data-ttu-id="56f68-142">Para recolher todo o lote para o comando `GO` , clique no sinal de menos na linha `CREATE PROCEDURE` .</span><span class="sxs-lookup"><span data-stu-id="56f68-142">To collapse the whole batch to the `GO` command, click the minus sign on the `CREATE PROCEDURE` line.</span></span> <span data-ttu-id="56f68-143">Não é possível recolher as linhas `SELECT GETDATE()` ou `SELECT @@VERSION` individualmente, pois elas são instruções de linha única e não têm regiões de estrutura de tópicos.</span><span class="sxs-lookup"><span data-stu-id="56f68-143">You cannot collapse the `SELECT GETDATE()` or `SELECT @@VERSION` lines individually because they are single line statements and do not get outlining regions.</span></span>


