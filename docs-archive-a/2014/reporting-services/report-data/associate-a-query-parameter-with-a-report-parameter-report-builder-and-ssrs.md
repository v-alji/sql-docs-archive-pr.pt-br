---
title: Associar um parâmetro de consulta a um parâmetro de relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- queries [Reporting Services], parameters
- parameters [Reporting Services], queries
ms.assetid: 6d297e1a-ff71-472a-addc-349e863092b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f65aa36e8910378d68963c8c9990518b661025ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679723"
---
# <a name="associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="82a5c-102">Associar um parâmetro de consulta a um parâmetro de relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="82a5c-102">Associate a Query Parameter with a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="82a5c-103">Quando você define uma consulta de conjunto de dados que contém uma variável de consulta, o comando de consulta é analisado.</span><span class="sxs-lookup"><span data-stu-id="82a5c-103">When you define a dataset query that contains a query variable, the query command is parsed.</span></span> <span data-ttu-id="82a5c-104">Para cada variável de consulta, são criados um parâmetro de conjunto de dados e um parâmetro de relatório correspondentes.</span><span class="sxs-lookup"><span data-stu-id="82a5c-104">For each query variable, a corresponding dataset parameter and report parameter are created.</span></span> <span data-ttu-id="82a5c-105">O parâmetro de conjunto de dados aponta para o parâmetro de relatório.</span><span class="sxs-lookup"><span data-stu-id="82a5c-105">The dataset parameter points to the report parameter.</span></span> <span data-ttu-id="82a5c-106">Dessa forma, o usuário pode inserir um valor que é passado diretamente para a consulta.</span><span class="sxs-lookup"><span data-stu-id="82a5c-106">This enables a user to enter a value that passes directly to the query.</span></span> <span data-ttu-id="82a5c-107">Toda vez que você edita o comando de consulta, ocorre o mesmo processo.</span><span class="sxs-lookup"><span data-stu-id="82a5c-107">Each time you edit the query command, the same process takes place.</span></span>  
  
 <span data-ttu-id="82a5c-108">Se você renomear o parâmetro de relatório associado a um parâmetro de consulta, deverá vincular manualmente os parâmetros de consulta ao parâmetro de relatório renomeado usando o procedimento descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="82a5c-108">If you rename a report parameter that is bound to a query parameter, you need to manually link the query parameters to the renamed report parameter by using the procedure in this topic.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-query-parameter-with-a-report-parameter"></a><span data-ttu-id="82a5c-109">Para associar um parâmetro de consulta a um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="82a5c-109">To associate a query parameter with a report parameter</span></span>  
  
1.  <span data-ttu-id="82a5c-110">No painel de dados do relatório, clique com o botão direito do mouse no conjunto de dados, clique em **Propriedades do Conjunto de Dados**e, depois, em **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="82a5c-110">In the Report Data pane, right-click the dataset, click **Dataset Properties**, and then click **Parameters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="82a5c-111"> Se o painel de dados do relatório não estiver visível, clique em **Dados do Relatório** no menu **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="82a5c-111">If the Report Data pane is not visible, click **Report Data** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="82a5c-112">Na coluna **Nome do Parâmetro**, localize o nome do parâmetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="82a5c-112">In the column **Parameter Name**, find the name of the query parameter.</span></span> <span data-ttu-id="82a5c-113">Os nomes de parâmetro são preenchidos automaticamente com base na consulta.</span><span class="sxs-lookup"><span data-stu-id="82a5c-113">Parameter names are automatically populated based on the query.</span></span> <span data-ttu-id="82a5c-114">Sempre que você altera a consulta, ela é verificada em busca de novos parâmetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="82a5c-114">Every time you change the query, the query is checked for new query parameters.</span></span> <span data-ttu-id="82a5c-115">Os parâmetros de consulta criados manualmente não são alterados quando a consulta é alterada.</span><span class="sxs-lookup"><span data-stu-id="82a5c-115">Query parameters that you create manually are not changed when the query changes.</span></span>  
  
    -   <span data-ttu-id="82a5c-116">Em **Nome do Parâmetro**, localize o nome do parâmetro de consulta conforme exibido na consulta.</span><span class="sxs-lookup"><span data-stu-id="82a5c-116">In **Parameter Name**, find the query parameter name as it exists in the query.</span></span> <span data-ttu-id="82a5c-117">Você também pode adicionar manualmente um novo parâmetro de consulta e inserir um nome.</span><span class="sxs-lookup"><span data-stu-id="82a5c-117">You can also manually add a new query parameter and enter a name.</span></span>  
  
    -   <span data-ttu-id="82a5c-118">Em **Valor do Parâmetro**, digite ou selecione uma expressão avaliada como o valor passado para o parâmetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="82a5c-118">In **Parameter Value**, type or select an expression that evaluates to the value to pass to the query parameter.</span></span> <span data-ttu-id="82a5c-119">Normalmente é o nome do parâmetro de relatório.</span><span class="sxs-lookup"><span data-stu-id="82a5c-119">This is typically the name of the report parameter.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="82a5c-120">Os valores de um parâmetro de consulta não se limitam a parâmetros de relatório.</span><span class="sxs-lookup"><span data-stu-id="82a5c-120">You are not limited to report parameters as values for a query parameter.</span></span> <span data-ttu-id="82a5c-121">Para o valor do parâmetro, você pode usar qualquer expressão avaliada como um valor.</span><span class="sxs-lookup"><span data-stu-id="82a5c-121">You can use any expression that evaluates to a value for the parameter value.</span></span>  
  
3.  <span data-ttu-id="82a5c-122">Repita a etapa 2 para especificar mais parâmetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="82a5c-122">Repeat step 2 for additional query parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a5c-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82a5c-123">See Also</span></span>  
 <span data-ttu-id="82a5c-124">[Conjuntos de itens de relatório inseridos e conjuntos de &#40;compartilhados Construtor de Relatórios e SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="82a5c-124">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="82a5c-125">Conceito de parâmetros de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="82a5c-125">Report Parameters Concept &#40;Report Builder and SSRS&#41;</span></span>](../report-design/report-parameters-concepts-report-builder-and-ssrs.md)  
  
  
