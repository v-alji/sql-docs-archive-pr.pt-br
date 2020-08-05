---
title: Adicionar um sub-relatório e parâmetros (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10093"
- sql12.rtp.rptdesigner.subreportproperties.general.f1
ms.assetid: 94f960f8-a629-4f1e-8277-c3b8f0680d98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3aeede343763ea5fc8fbdfde179208f98fa1a2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569094"
---
# <a name="add-a-subreport-and-parameters-report-builder-and-ssrs"></a><span data-ttu-id="c15e4-102">Adicionar um sub-relatório e parâmetros (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c15e4-102">Add a Subreport and Parameters (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c15e4-103">Adicione sub-relatórios a um relatório quando quiser criar um relatório principal que seja um contêiner para vários relatórios relacionados.</span><span class="sxs-lookup"><span data-stu-id="c15e4-103">Add subreports to a report when you want to create a main report that is a container for multiple related reports.</span></span> <span data-ttu-id="c15e4-104">Um sub-relatório é uma referência a outro relatório.</span><span class="sxs-lookup"><span data-stu-id="c15e4-104">A subreport is a reference to another report.</span></span> <span data-ttu-id="c15e4-105">Para relacionar os relatórios por valores de dados (por exemplo, para que diversos relatórios exibam dados para o mesmo cliente), é preciso criar um relatório com parâmetros (por exemplo, um relatório que exiba os detalhes de um cliente específico) como o sub-relatório.</span><span class="sxs-lookup"><span data-stu-id="c15e4-105">To relate the reports through data values (for example, to have multiple reports show data for the same customer), you must design a parameterized report (for example, a report that shows the details for a specific customer) as the subreport.</span></span> <span data-ttu-id="c15e4-106">Ao adicionar um sub-relatório ao relatório principal, você também pode especificar os parâmetros que serão passados para o sub-relatório.</span><span class="sxs-lookup"><span data-stu-id="c15e4-106">When you add a subreport to the main report, you can specify parameters to pass to the subreport.</span></span>  
  
 <span data-ttu-id="c15e4-107">Também é possível adicionar sub-relatórios a linhas ou colunas dinâmicas em uma tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="c15e4-107">You can also add subreports to dynamic rows or columns in a table or matrix.</span></span> <span data-ttu-id="c15e4-108">Quando o relatório principal é processado, o sub-relatório é processado para cada linha.</span><span class="sxs-lookup"><span data-stu-id="c15e4-108">When the main report is processed, the subreport is processed for each row.</span></span> <span data-ttu-id="c15e4-109">Nesse caso, analise se você pode obter o efeito desejado usando regiões de dados ou regiões de dados aninhados.</span><span class="sxs-lookup"><span data-stu-id="c15e4-109">In this case, consider whether you can achieve the desired effect by using data regions or nested data regions.</span></span>  
  
 <span data-ttu-id="c15e4-110">Para adicionar um sub-relatório a um relatório, crie primeiro o relatório que atuará como sub-relatório.</span><span class="sxs-lookup"><span data-stu-id="c15e4-110">To add a subreport to a report, you must first create the report that will act as the subreport.</span></span> <span data-ttu-id="c15e4-111">Para obter mais informações sobre como criar o sub-relatório, consulte [Sub-relatórios &#40;Construtor de Relatórios e SSRS&#41;](subreports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c15e4-111">For more information on creating the subreport, see [Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-subreport"></a><span data-ttu-id="c15e4-112">Para adicionar um sub-relatório</span><span class="sxs-lookup"><span data-stu-id="c15e4-112">To add a subreport</span></span>  
  
1.  <span data-ttu-id="c15e4-113">Na guia **Inserir** , clique em **Sub-relatório**.</span><span class="sxs-lookup"><span data-stu-id="c15e4-113">On the **Insert** tab, click **Subreport**.</span></span>  
  
2.  <span data-ttu-id="c15e4-114">Na superfície de design, clique em um local no relatório e arraste a caixa até obter o tamanho desejado para o sub-relatório.</span><span class="sxs-lookup"><span data-stu-id="c15e4-114">On the design surface, click a location on the report and then drag a box to the desired size of the subreport.</span></span> <span data-ttu-id="c15e4-115">Se preferir, clique na superfície de design para criar um sub-relatório de tamanho padrão.</span><span class="sxs-lookup"><span data-stu-id="c15e4-115">Alternatively, click the design surface to create a subreport of default size.</span></span>  
  
3.  <span data-ttu-id="c15e4-116">Clique com o botão direito do mouse no sub-relatório e clique em **Propriedades do sub-relatório**.</span><span class="sxs-lookup"><span data-stu-id="c15e4-116">Right-click the subreport, and then click **Subreport Properties**.</span></span>  
  
4.  <span data-ttu-id="c15e4-117">Na caixa de diálogo **Propriedades do Sub-relatório** , digite um nome na caixa de texto **Nome** ou aceite o nome padrão.</span><span class="sxs-lookup"><span data-stu-id="c15e4-117">In the **Subreport Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span> <span data-ttu-id="c15e4-118">O nome deve ser exclusivo no relatório.</span><span class="sxs-lookup"><span data-stu-id="c15e4-118">The name must be unique within the report.</span></span> <span data-ttu-id="c15e4-119">Por padrão, um nome geral, como Subreport1 ou Subreport2, é atribuído.</span><span class="sxs-lookup"><span data-stu-id="c15e4-119">By default, a general name such as Subreport1 or Subreport2 is assigned.</span></span>  
  
5.  <span data-ttu-id="c15e4-120">Na caixa **Usar este relatório como sub-relatório** , clique em **Procurar**ou digite o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="c15e4-120">In the **Use this report as a subreport** box, click **Browse**, or type the name of the report.</span></span> <span data-ttu-id="c15e4-121">É preferível clicar em **Procurar** porque o caminho para o sub-relatório será especificado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c15e4-121">Clicking **Browse** is preferred because the path to the subreport will be specified automatically.</span></span> <span data-ttu-id="c15e4-122">Você pode especificar o relatório de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="c15e4-122">You can specify the report in the several ways.</span></span> <span data-ttu-id="c15e4-123">Para obter mais informações, consulte [Especificando caminhos para itens externos &#40;Construtor de Relatórios e SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c15e4-123">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="c15e4-124">(Opcional) Clique em **Sim** para **Omitir borda na quebra de página** para impedir que uma borda seja renderizada no meio do sub-relatório caso o sub-relatório se expanda por mais de uma página.</span><span class="sxs-lookup"><span data-stu-id="c15e4-124">(Optional) Click **Yes** for **Omit border on page break** to prevent a border from being rendered in the middle of the subreport if the subreport spans more than one page.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-specify-parameters-to-pass-to-a-subreport"></a><span data-ttu-id="c15e4-125">Para especificar os parâmetros que serão passados para um sub-relatório</span><span class="sxs-lookup"><span data-stu-id="c15e4-125">To specify parameters to pass to a subreport</span></span>  
  
1.  <span data-ttu-id="c15e4-126">No modo de exibição de Design, clique com o botão direito do mouse no sub-relatório e clique em **Propriedades do sub-relatório**.</span><span class="sxs-lookup"><span data-stu-id="c15e4-126">In Design view, right-click the subreport and then click **Subreport Properties**.</span></span>  
  
2.  <span data-ttu-id="c15e4-127">Na caixa de diálogo **Propriedades do Sub-relatório** , clique em **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="c15e4-127">In the **Subreport Properties** dialog box, click **Parameters**.</span></span>  
  
3.  <span data-ttu-id="c15e4-128">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c15e4-128">Click **Add**.</span></span> <span data-ttu-id="c15e4-129">Uma linha nova é adicionada à grade de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="c15e4-129">A new row is added to the parameter grid.</span></span>  
  
4.  <span data-ttu-id="c15e4-130">Na caixa de texto **de Nome** , digite o nome de um parâmetro no sub-relatório ou escolha-o na caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="c15e4-130">In the **Name** text box, type the name of a parameter in the subreport or choose it from the list box.</span></span> <span data-ttu-id="c15e4-131">Esse nome deve corresponder a um parâmetro de relatório, não a um parâmetro de consulta, no sub-relatório.</span><span class="sxs-lookup"><span data-stu-id="c15e4-131">This name must match a report parameter, not a query parameter, in the subreport.</span></span>  
  
5.  <span data-ttu-id="c15e4-132">Na caixa de listagem **Valor** , digite ou selecione um valor a ser passado para o sub-relatório.</span><span class="sxs-lookup"><span data-stu-id="c15e4-132">In the **Value** list box, type or select a value to pass to the subreport.</span></span> <span data-ttu-id="c15e4-133">Esse valor pode ser um texto estático ou uma expressão que referencie um campo ou outro objeto no relatório principal.</span><span class="sxs-lookup"><span data-stu-id="c15e4-133">This value can be static text or an expression that references a field or other object in the main report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c15e4-134">No Construtor de Relatórios, se um parâmetro estiver ausente na lista **Parâmetros** , e se o sub-relatório tiver um valor padrão definido, o sub-relatório será processado corretamente.</span><span class="sxs-lookup"><span data-stu-id="c15e4-134">In Report Builder, if a parameter is missing from the **Parameters** list and the subreport has a default value defined, the subreport will be processed correctly.</span></span>  
    >   
    >  <span data-ttu-id="c15e4-135">No Designer de Relatórios, todos os parâmetros exigidos pelo sub-relatório devem estar incluídos na lista **Parâmetros** .</span><span class="sxs-lookup"><span data-stu-id="c15e4-135">In Report Designer, all parameters that are required by the subreport must be included in the **Parameters** list.</span></span> <span data-ttu-id="c15e4-136">Se estiver faltando um parâmetro obrigatório, o sub-relatório não será exibido corretamente no relatório principal.</span><span class="sxs-lookup"><span data-stu-id="c15e4-136">If a required parameter is missing, the subreport is not displayed correctly in the main report.</span></span>  
  
6.  <span data-ttu-id="c15e4-137">Repita as etapas de 3 a 5 para especificar um nome e um valor para cada parâmetro do sub-relatório.</span><span class="sxs-lookup"><span data-stu-id="c15e4-137">Repeat steps 3-5 to specify a name and value for each subreport parameter.</span></span>  
  
7.  <span data-ttu-id="c15e4-138">Para excluir um parâmetro de sub-relatório, clique no parâmetro na grade de parâmetros e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="c15e4-138">To delete a subreport parameter, click the parameter in the parameter grid, and then click **Delete**.</span></span>  
  
8.  <span data-ttu-id="c15e4-139">Para alterar a ordem de um parâmetro de sub-relatório, clique no parâmetro e clique no botão de seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="c15e4-139">To change the order of a subreport parameter, click the parameter, and then click the up button or the down button.</span></span>  
  
     <span data-ttu-id="c15e4-140">A alteração da ordem de um parâmetro de sub-relatório não afeta o processamento do sub-relatório.</span><span class="sxs-lookup"><span data-stu-id="c15e4-140">Changing the order of a subreport parameter does not affect the processing of the subreport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c15e4-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c15e4-141">See Also</span></span>  
 <span data-ttu-id="c15e4-142">[Sub-relatórios &#40;Construtor de Relatórios e SSRS&#41;](subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c15e4-142">[Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c15e4-143">Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c15e4-143">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
