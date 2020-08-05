---
title: Ações em modelos multidimensionais | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- actions [Analysis Services], creating
- report actions [Analysis Services]
- drillthrough actions [Analysis Services]
- cubes [Analysis Services], actions
ms.assetid: b9fee2b9-05a5-4077-848d-d8457326dc27
author: minewiskan
ms.author: owend
ms.openlocfilehash: ce42907190363be085e8f4d8e9adfbab52a70590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572763"
---
# <a name="actions-in-multidimensional-models"></a><span data-ttu-id="fcd9b-102">Ações em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="fcd9b-102">Actions in Multidimensional Models</span></span>
  <span data-ttu-id="fcd9b-103">Uma ação é uma operação iniciada pelo usuário final em um cubo selecionado ou em parte de um cubo.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-103">An action is an end user-initiated operation upon a selected cube or portion of a cube.</span></span> <span data-ttu-id="fcd9b-104">A operação pode iniciar um aplicativo com o item selecionado como parâmetro ou pode recuperar informações sobre o item selecionado.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-104">The operation can start an application with the selected item as a parameter, or it can retrieve information about the selected item.</span></span> <span data-ttu-id="fcd9b-105">Para obter mais informações sobre ações, consulte [Ações &#40;Analysis Services – Dados Multidimensionais&#41;](actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="fcd9b-105">For more information about actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](actions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="fcd9b-106">Use a guia **Ações** do Designer de Cubo para criar ações para um cubo.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-106">Use the **Actions** tab of Cube Designer to build actions for a cube.</span></span> <span data-ttu-id="fcd9b-107">Especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fcd9b-107">Specify the following:</span></span>  
  
 <span data-ttu-id="fcd9b-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-108">**Name**</span></span>  
 <span data-ttu-id="fcd9b-109">Selecione um nome que identifica a ação.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-109">Select a name that identifies the action.</span></span>  
  
 <span data-ttu-id="fcd9b-110">**Destino da Ação**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-110">**Action Target**</span></span>  
 <span data-ttu-id="fcd9b-111">Selecione o objeto ao qual a ação será anexada.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-111">Select the object to which the action is attached.</span></span> <span data-ttu-id="fcd9b-112">Em geral, em aplicativos cliente, a ação é exibida quando os usuários finais selecionam o objeto de destino; no entanto, o aplicativo cliente determina qual operação do usuário final exibe ações.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-112">Generally, in client applications, the action is displayed when end users select the target object; however, the client application determines which end-user operation displays actions.</span></span> <span data-ttu-id="fcd9b-113">Para **Tipo de destino**, selecione entre os objetos a seguir:</span><span class="sxs-lookup"><span data-stu-id="fcd9b-113">For **Target type**, select from the following objects:</span></span>  
  
-   <span data-ttu-id="fcd9b-114">Membros de atributo</span><span class="sxs-lookup"><span data-stu-id="fcd9b-114">Attribute members</span></span>  
  
-   <span data-ttu-id="fcd9b-115">Células</span><span class="sxs-lookup"><span data-stu-id="fcd9b-115">Cells</span></span>  
  
-   <span data-ttu-id="fcd9b-116">Cubo</span><span class="sxs-lookup"><span data-stu-id="fcd9b-116">Cube</span></span>  
  
-   <span data-ttu-id="fcd9b-117">Membros de dimensão</span><span class="sxs-lookup"><span data-stu-id="fcd9b-117">Dimension members</span></span>  
  
-   <span data-ttu-id="fcd9b-118">Hierarquia</span><span class="sxs-lookup"><span data-stu-id="fcd9b-118">Hierarchy</span></span>  
  
-   <span data-ttu-id="fcd9b-119">Membros de hierarquia</span><span class="sxs-lookup"><span data-stu-id="fcd9b-119">Hierarchy members</span></span>  
  
-   <span data-ttu-id="fcd9b-120">Nível</span><span class="sxs-lookup"><span data-stu-id="fcd9b-120">Level</span></span>  
  
-   <span data-ttu-id="fcd9b-121">Membros de nível</span><span class="sxs-lookup"><span data-stu-id="fcd9b-121">Level members</span></span>  
  
 <span data-ttu-id="fcd9b-122">Depois de selecionar o tipo de objeto de destino, em **Objeto de destino**, selecione o objeto de cubo do tipo designado.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-122">After you select the target object type, under **Target object**, select the cube object of the designated type.</span></span>  
  
 <span data-ttu-id="fcd9b-123">**Condição (Opcional)**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-123">**Condition (Optional)**</span></span>  
 <span data-ttu-id="fcd9b-124">Especifique uma expressão MDX opcional que resolve um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-124">Specify an optional Multidimensional Expressions (MDX) expression that resolves to a Boolean value.</span></span> <span data-ttu-id="fcd9b-125">Se o valor for `True`, a ação será executada no destino especificado.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-125">If the value is `True`, the action is performed on the specified target.</span></span> <span data-ttu-id="fcd9b-126">Se for `False`, a ação não será executada.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-126">If the value is `False`, the action is not performed.</span></span>  
  
 <span data-ttu-id="fcd9b-127">**Conteúdo da Ação**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-127">**Action Content**</span></span>  
 <span data-ttu-id="fcd9b-128">Selecione o tipo de ação.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-128">Select the type of action.</span></span> <span data-ttu-id="fcd9b-129">A tabela a seguir resume os tipos disponíveis:</span><span class="sxs-lookup"><span data-stu-id="fcd9b-129">The following table summarizes the available types.</span></span>  
  
|<span data-ttu-id="fcd9b-130">Type</span><span class="sxs-lookup"><span data-stu-id="fcd9b-130">Type</span></span>|<span data-ttu-id="fcd9b-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="fcd9b-131">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="fcd9b-132">Conjunto de Dados</span><span class="sxs-lookup"><span data-stu-id="fcd9b-132">Data Set</span></span>|<span data-ttu-id="fcd9b-133">Recupera um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-133">Retrieves a dataset.</span></span>|  
|<span data-ttu-id="fcd9b-134">Proprietário</span><span class="sxs-lookup"><span data-stu-id="fcd9b-134">Proprietary</span></span>|<span data-ttu-id="fcd9b-135">Executa uma operação usando uma interface diferente das listadas nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-135">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="fcd9b-136">Conjunto de Linhas</span><span class="sxs-lookup"><span data-stu-id="fcd9b-136">Row Set</span></span>|<span data-ttu-id="fcd9b-137">Recupera um conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-137">Retrieves a rowset.</span></span>|  
|<span data-ttu-id="fcd9b-138">Instrução</span><span class="sxs-lookup"><span data-stu-id="fcd9b-138">Statement</span></span>|<span data-ttu-id="fcd9b-139">Executa um comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-139">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="fcd9b-140">URL</span><span class="sxs-lookup"><span data-stu-id="fcd9b-140">URL</span></span>|<span data-ttu-id="fcd9b-141">Exibe uma página variável em um navegador de Internet.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-141">Displays a variable page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="fcd9b-142">Para **Expressão da Ação**, especifique os parâmetros que são passados quando a ação é executada.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-142">For **Action Expression**, specify the parameters that are passed when the action is run.</span></span> <span data-ttu-id="fcd9b-143">A sintaxe deve avaliar uma cadeia de caracteres e você deve incluir uma expressão escrita em MDX.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-143">The syntax must evaluate to a string, and you must include an expression written in MDX.</span></span> <span data-ttu-id="fcd9b-144">Por exemplo, a expressão MDX pode indicar uma parte do cubo incluída na sintaxe.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-144">For example, your MDX expression can indicate a part of the cube that is included in the syntax.</span></span> <span data-ttu-id="fcd9b-145">Expressões MDX são avaliadas antes de os parâmetros serem passados.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-145">MDX expressions are evaluated before the parameters are passed.</span></span> <span data-ttu-id="fcd9b-146">Além disso, o Construtor MDX está disponível para lhe ajudar a construir expressões MDX.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-146">Also, MDX Builder is available to help you build MDX expressions.</span></span>  
  
 <span data-ttu-id="fcd9b-147">**Propriedades Adicionais**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-147">**Additional Properties**</span></span>  
 <span data-ttu-id="fcd9b-148">Selecione a propriedade.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-148">Select the property.</span></span> <span data-ttu-id="fcd9b-149">A tabela a seguir resume as propriedades disponíveis:</span><span class="sxs-lookup"><span data-stu-id="fcd9b-149">The following table summarizes the available properties.</span></span>  
  
|<span data-ttu-id="fcd9b-150">Propriedade</span><span class="sxs-lookup"><span data-stu-id="fcd9b-150">Property</span></span>|<span data-ttu-id="fcd9b-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="fcd9b-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="fcd9b-152">**Invocação**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-152">**Invocation**</span></span>|<span data-ttu-id="fcd9b-153">Especifica como a ação é executada.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-153">Specifies how the action is run.</span></span> <span data-ttu-id="fcd9b-154">Interativo, o padrão, especifica que a ação será executada quando um usuário acessar um objeto.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-154">Interactive, the default, specifies that the action is run when a user accesses an object.</span></span> <span data-ttu-id="fcd9b-155">Os configurações possíveis são:</span><span class="sxs-lookup"><span data-stu-id="fcd9b-155">The possible settings are:</span></span><br /><br /> <span data-ttu-id="fcd9b-156">Lote</span><span class="sxs-lookup"><span data-stu-id="fcd9b-156">Batch</span></span><br /><br /> <span data-ttu-id="fcd9b-157">Interativo</span><span class="sxs-lookup"><span data-stu-id="fcd9b-157">Interactive</span></span><br /><br /> <span data-ttu-id="fcd9b-158">Em Aberto</span><span class="sxs-lookup"><span data-stu-id="fcd9b-158">On Open</span></span>|  
|<span data-ttu-id="fcd9b-159">**Aplicativo**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-159">**Application**</span></span>|<span data-ttu-id="fcd9b-160">Descreve o aplicativo da ação.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-160">Describes the application of the action.</span></span>|  
|<span data-ttu-id="fcd9b-161">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-161">**Description**</span></span>|<span data-ttu-id="fcd9b-162">Descreve a ação.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-162">Describes the action.</span></span>|  
|<span data-ttu-id="fcd9b-163">**Legenda**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-163">**Caption**</span></span>|<span data-ttu-id="fcd9b-164">Fornece uma legenda que é exibida para a ação.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-164">Provides a caption that is displayed for the action.</span></span> <span data-ttu-id="fcd9b-165">Se a legenda for MDX, especifique `True` for **Caption é MDX**.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-165">If the caption is MDX, specify `True` for **Caption is MDX**.</span></span>|  
|<span data-ttu-id="fcd9b-166">**A legenda é MDX**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-166">**Caption is MDX**</span></span>|<span data-ttu-id="fcd9b-167">Especifique `True` se a legenda for MDX ou `False` se não for.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-167">Specify `True` if the caption is MDX or `False` if it is not.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="fcd9b-168">Use o Analysis Services Scripting Language (ASSL) ou o Objetos de Gerenciamento de Análise (AMO) para definir tipos de ação HTML ou de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-168">You must use Analysis Services Scripting Language (ASSL) or Analysis Management Objects (AMO) to define HTML and Command Line action types.</span></span> <span data-ttu-id="fcd9b-169">Para obter mais informações, consulte [Elemento Action &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Elemento Type &#40;Ação&#41; &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl) e [Programando objetos OLAP AMO avançados](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span><span class="sxs-lookup"><span data-stu-id="fcd9b-169">For more information, see [Action Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Type Element &#40;Action&#41; &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl), and [Programming AMO OLAP Advanced Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span></span>  
  
## <a name="creating-a-reporting-action"></a><span data-ttu-id="fcd9b-170">Criando uma ação de relatório</span><span class="sxs-lookup"><span data-stu-id="fcd9b-170">Creating a Reporting Action</span></span>  
 <span data-ttu-id="fcd9b-171">O servidor de relatório responde a solicitações baseadas na URL para relatórios.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-171">The report server responds to URL-based requests for reports.</span></span> <span data-ttu-id="fcd9b-172">Para criar uma ação de relatório, no menu **Cubo** , clique em **Nova Ação de Relatório**.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-172">To create a reporting action, on the **Cube** menu, click **New Reporting Action**.</span></span> <span data-ttu-id="fcd9b-173">As opções a seguir são específicas de uma ação de relatório.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-173">The following options are specific to a reporting action.</span></span>  
  
 <span data-ttu-id="fcd9b-174">**Servidor de relatório**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-174">**Report Server**</span></span>  
 <span data-ttu-id="fcd9b-175">As propriedades descritas na tabela a seguir são especificadas para o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-175">The properties described in the following table are specified for the report server.</span></span>  
  
|<span data-ttu-id="fcd9b-176">Propriedade</span><span class="sxs-lookup"><span data-stu-id="fcd9b-176">Property</span></span>|<span data-ttu-id="fcd9b-177">Descrição</span><span class="sxs-lookup"><span data-stu-id="fcd9b-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="fcd9b-178">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-178">**Server name**</span></span>|<span data-ttu-id="fcd9b-179">O nome do computador que executa o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-179">The name of the computer running report server.</span></span>|  
|<span data-ttu-id="fcd9b-180">**Caminho do servidor**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-180">**Server path**</span></span>|<span data-ttu-id="fcd9b-181">O caminho exibido pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-181">The path exposed by report server.</span></span>|  
|<span data-ttu-id="fcd9b-182">**Formato do relatório**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-182">**Report format**</span></span>|<span data-ttu-id="fcd9b-183">HTML5, HTML3, Excel ou PDF.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-183">HTML5, HTML3, Excel, or PDF.</span></span>|  
  
 <span data-ttu-id="fcd9b-184">**Parâmetros (Opcional)**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-184">**Parameters (Optional)**</span></span>  
 <span data-ttu-id="fcd9b-185">Os parâmetros serão enviados ao servidor como parte da cadeia de caracteres de URL quando a ação for criada.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-185">The parameters are sent to the server as part of the URL string when the action is created.</span></span> <span data-ttu-id="fcd9b-186">Incluem **Nome do Parâmetro** e **Valor do Parâmetro**, que são uma expressão MDX.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-186">They include **Parameter Name** and **Parameter Value**, which is an MDX expression.</span></span>  
  
 <span data-ttu-id="fcd9b-187">A URL do servidor de relatório é construída da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fcd9b-187">The report server URL is constructed as follows:</span></span>  
  
```  
  
http://  
host  
/  
virtualdirectory  
/Path&  
parametername1  
=  
parametervalue1  
& ...  
```  
  
 <span data-ttu-id="fcd9b-188">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fcd9b-188">For example:</span></span>  
  
```  
http://localhost/ReportServer/Sales/YearlySalesByCategory?rs:Command=Render&Region=West  
```  
  
## <a name="creating-a-drillthrough-action"></a><span data-ttu-id="fcd9b-189">Criando um ação de detalhamento</span><span class="sxs-lookup"><span data-stu-id="fcd9b-189">Creating a Drillthrough Action</span></span>  
 <span data-ttu-id="fcd9b-190">Uma ação de extração de detalhes é definida por uma ação de conjunto de linhas, retornada ao aplicativo cliente como uma instrução de extração de detalhes.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-190">A drillthrough action is defined by a rowset action, which is returned to the client application as a drillthrough statement.</span></span> <span data-ttu-id="fcd9b-191">O destino de ação é um membro de um grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-191">The action target is a member of a measure group.</span></span> <span data-ttu-id="fcd9b-192">Para criar uma nova ação de drillthrough, no menu **Cubo** , clique em **Nova Ação de Drillthrough**.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-192">To create a new drillthrough action, on the **Cube** menu, click **New Drillthrough Action**.</span></span> <span data-ttu-id="fcd9b-193">As opções a seguir são específicas de uma ação de extração de detalhes:</span><span class="sxs-lookup"><span data-stu-id="fcd9b-193">The following options are specific to a drillthrough action:</span></span>  
  
 <span data-ttu-id="fcd9b-194">**Colunas de Extração de Detalhes**</span><span class="sxs-lookup"><span data-stu-id="fcd9b-194">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="fcd9b-195">Selecione uma ou mais dimensões e, para cada uma, as colunas de detalhamento retornadas ao aplicativo cliente pela ação.</span><span class="sxs-lookup"><span data-stu-id="fcd9b-195">Select one or more dimensions and, for each dimension, the drillthrough columns returned to the client application by the action.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd9b-196">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fcd9b-196">See Also</span></span>  
 [<span data-ttu-id="fcd9b-197">Cubos em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="fcd9b-197">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
