---
title: Exibir números de página ou outras propriedades do relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7d95245-4709-4d04-acb4-59bf71e60d97
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: efc3d5d5de11af1fcdfefc52ed12d5057ee12668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573740"
---
# <a name="display-page-numbers-or-other-report-properties-report-builder-and-ssrs"></a><span data-ttu-id="395f9-102">Exibir números de página ou outras propriedades do relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="395f9-102">Display Page Numbers or Other Report Properties (Report Builder and SSRS)</span></span>
  <span data-ttu-id="395f9-103">É fácil adicionar números de página, um título de relatório, nome de arquivo e outras propriedades de relatório aos cabeçalhos ou rodapés de seu relatório.</span><span class="sxs-lookup"><span data-stu-id="395f9-103">It's easy to add page numbers, a report title, file name, and other report properties to the page headers or footers of your report.</span></span> <span data-ttu-id="395f9-104">Essas propriedades são armazenadas como campos na pasta Campos Internos no painel de dados do relatório:</span><span class="sxs-lookup"><span data-stu-id="395f9-104">These properties are stored as fields in the Built-in Fields folder in the Report Data pane:</span></span>  
  
-   <span data-ttu-id="395f9-105">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="395f9-105">Execution time</span></span>  
  
-   <span data-ttu-id="395f9-106">Número da página</span><span class="sxs-lookup"><span data-stu-id="395f9-106">Page number</span></span>  
  
-   <span data-ttu-id="395f9-107">Pasta Relatório</span><span class="sxs-lookup"><span data-stu-id="395f9-107">Report folder</span></span>  
  
-   <span data-ttu-id="395f9-108">Nome do relatório</span><span class="sxs-lookup"><span data-stu-id="395f9-108">Report name</span></span>  
  
-   <span data-ttu-id="395f9-109">URL do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="395f9-109">Report server URL</span></span>  
  
-   <span data-ttu-id="395f9-110">Total de páginas</span><span class="sxs-lookup"><span data-stu-id="395f9-110">Total pages</span></span>  
  
-   <span data-ttu-id="395f9-111">Id de Usuário</span><span class="sxs-lookup"><span data-stu-id="395f9-111">User ID</span></span>  
  
-   <span data-ttu-id="395f9-112">Linguagem</span><span class="sxs-lookup"><span data-stu-id="395f9-112">Language</span></span>  
  
 <span data-ttu-id="395f9-113">Para um número de página, talvez você queira adicionar a palavra "Página" antes do número.</span><span class="sxs-lookup"><span data-stu-id="395f9-113">For a page number, you may want to add the word "Page" before the number.</span></span> <span data-ttu-id="395f9-114">Você também pode desejar mostrar o número total de páginas.</span><span class="sxs-lookup"><span data-stu-id="395f9-114">You may also want to show the total number of pages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="395f9-115">A adição do número total de páginas ao rodapé pode reduzir a velocidade desempenho quando você executar ou visualizar seu relatório.</span><span class="sxs-lookup"><span data-stu-id="395f9-115">Adding the total number of pages to the footer may slow performance when you run or preview your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-number-or-other-report-properties"></a><span data-ttu-id="395f9-116">Para adicionar um número de página ou outras propriedades de relatório</span><span class="sxs-lookup"><span data-stu-id="395f9-116">To add a page number or other report properties</span></span>  
  
1.  <span data-ttu-id="395f9-117">No painel de dados do relatório, expanda a pasta Campos Internos.</span><span class="sxs-lookup"><span data-stu-id="395f9-117">In the Report Data pane, expand the Built-in Fields folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="395f9-118">Se o painel de dados do relatório não estiver visível, na guia Exibir, clique em **Dados do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="395f9-118">If you don't see the Report Data pane, on the View tab, check **Report Data**.</span></span>  
  
2.  <span data-ttu-id="395f9-119">Arraste o campo **Número da Página** do painel de dados do relatório para o cabeçalho ou o rodapé do relatório.</span><span class="sxs-lookup"><span data-stu-id="395f9-119">Drag the **Page Number** field from the Report Data pane to the report header or footer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="395f9-120">O rodapé de página é adicionado automaticamente ao relatório.</span><span class="sxs-lookup"><span data-stu-id="395f9-120">The page footer is added to the report automatically.</span></span> <span data-ttu-id="395f9-121">Para adicionar um cabeçalho de página, na guia **Inserir** , clique em **Cabeçalho**e em **Adicionar Cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="395f9-121">To add a page header, on the **Insert** tab, click **Header**, and then click **Add Header**.</span></span>  
    >   
    >  <span data-ttu-id="395f9-122">Uma caixa de texto que contém a expressão simples [&PageNumber] é adicionada.</span><span class="sxs-lookup"><span data-stu-id="395f9-122">A text box that contains the simple expression [&PageNumber] is added.</span></span>  
  
### <a name="to-add-the-word-page-before-the-page-number"></a><span data-ttu-id="395f9-123">Para adicionar a palavra "Página" antes do número de página</span><span class="sxs-lookup"><span data-stu-id="395f9-123">To add the word "Page" before the page number</span></span>  
  
1.  <span data-ttu-id="395f9-124">Clique com o botão direito do mouse na caixa de texto que contém [&PageNumber] e clique em **Expressões**.</span><span class="sxs-lookup"><span data-stu-id="395f9-124">Right-click the text box that contains [&PageNumber] and click **Expressions**.</span></span>  
  
     <span data-ttu-id="395f9-125">A caixa de texto **Definir Expressão para: Valor** contém a expressão =Globals!PageNumber.</span><span class="sxs-lookup"><span data-stu-id="395f9-125">The **Set Expression for: Value** text box contains the expression =Globals!PageNumber.</span></span>  
  
2.  <span data-ttu-id="395f9-126">Coloque o cursor depois do sinal de = e digite `"Page " &`.</span><span class="sxs-lookup"><span data-stu-id="395f9-126">Place the cursor after the = sign and type `"Page " &`.</span></span>  
  
     <span data-ttu-id="395f9-127">Agora, a expressão é ="Página "&Globals! PageNumber</span><span class="sxs-lookup"><span data-stu-id="395f9-127">The expression is now  ="Page "&Globals!PageNumber</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-total-number-of-pages-after-the-page-number"></a><span data-ttu-id="395f9-128">Para adicionar o número total de páginas após o número de página</span><span class="sxs-lookup"><span data-stu-id="395f9-128">To add total number of pages after the page number</span></span>  
  
1.  <span data-ttu-id="395f9-129">Clique com o botão direito do mouse na caixa de texto com a expressão e clique em **Expressões**.</span><span class="sxs-lookup"><span data-stu-id="395f9-129">Right click the text box with the expression and click **Expressions**.</span></span>  
  
2.  <span data-ttu-id="395f9-130">Digite **&" de "&** no final da expressão.</span><span class="sxs-lookup"><span data-stu-id="395f9-130">Type **&" of "&** at the end of the expression.</span></span>  
  
3.  <span data-ttu-id="395f9-131">No painel Categoria, expanda **Campos Internos** e clique duas vezes em **TotalPages**.</span><span class="sxs-lookup"><span data-stu-id="395f9-131">In the Category pane, expand **Built-in Fields** and double-click **TotalPages**.</span></span>  
  
     <span data-ttu-id="395f9-132">Agora, a expressão é ="Página "&Globals!PageNumber &" de "&Globals!TotalPages</span><span class="sxs-lookup"><span data-stu-id="395f9-132">The expression is now ="Page "&Globals!PageNumber &" of "&Globals!TotalPages</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="395f9-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="395f9-133">See Also</span></span>  
 <span data-ttu-id="395f9-134">[Cabeçalhos e rodapés de página &#40;Construtor de Relatórios e SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="395f9-134">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="395f9-135">Formatar o texto em uma caixa de texto &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="395f9-135">Format Text in a Text Box &#40;Report Builder and SSRS&#41;</span></span>](format-text-in-a-text-box-report-builder-and-ssrs.md)  
  
  
