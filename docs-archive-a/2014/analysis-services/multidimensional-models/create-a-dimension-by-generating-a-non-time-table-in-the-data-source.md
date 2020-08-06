---
title: Criar uma dimensão gerando uma tabela que não seja de tempo na fonte de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data sources [Analysis Services], dimensions without data source
- dimensions [Analysis Services], standard
- dimensions [Analysis Services], creating without data source
- standard dimensions [Analysis Services]
ms.assetid: a37f7a46-7451-4582-ba19-2595196d97bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 49dbfb0c1fc15c1cbf703514e0fc693dfabf1e9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683774"
---
# <a name="create-a-dimension-by-generating-a-non-time-table-in-the-data-source"></a><span data-ttu-id="ddbd0-102">Criar uma dimensão ao gerar uma tabela que não seja de tempo na fonte de dados</span><span class="sxs-lookup"><span data-stu-id="ddbd0-102">Create a Dimension by Generating a Non-Time Table in the Data Source</span></span>
  <span data-ttu-id="ddbd0-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , você pode usar o assistente para dimensões no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para criar uma dimensão sem usar uma fonte de dados existente.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use the Dimension Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to create a dimension without using an existing data source.</span></span> <span data-ttu-id="ddbd0-104">Isso é possível selecionando a opção **Gerar uma tabela que não seja de tempo na fonte de dados** da página **Selecionar Método de Criação** do assistente.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-104">You do this by selecting the **Generate a non-time table in the data source** option of the **Select Creation Method** page of the wizard.</span></span> <span data-ttu-id="ddbd0-105">Para criar uma nova tabela de dimensão na fonte de dados subjacente, você precisa ter permissão para criar objetos na fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-105">To create a new dimension table in the underlying data source, you must have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="ddbd0-106">Ao definir uma dimensão sem uma exibição da fonte de dados predefinida, você pode definir a dimensão do zero ou pode usar um modelo de dimensão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-106">When defining a dimension without a predefined data source view, you can either define the dimension from scratch or use a dimension template.</span></span>  
  
 <span data-ttu-id="ddbd0-107">O Assistente para Dimensões fornece modelos de dimensão de exemplo, com os quais é possível construir um tipo de dimensão comum.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-107">The Dimension Wizard provides sample dimension templates from which you can build a common dimension type.</span></span> <span data-ttu-id="ddbd0-108">Você pode selecionar a partir dos seguintes tipos de dimensão:</span><span class="sxs-lookup"><span data-stu-id="ddbd0-108">You can select from the following types of dimensions:</span></span>  
  
-   <span data-ttu-id="ddbd0-109">Conta</span><span class="sxs-lookup"><span data-stu-id="ddbd0-109">Account</span></span>  
  
-   <span data-ttu-id="ddbd0-110">Cliente</span><span class="sxs-lookup"><span data-stu-id="ddbd0-110">Customer</span></span>  
  
-   <span data-ttu-id="ddbd0-111">Data</span><span class="sxs-lookup"><span data-stu-id="ddbd0-111">Date</span></span>  
  
-   <span data-ttu-id="ddbd0-112">department</span><span class="sxs-lookup"><span data-stu-id="ddbd0-112">Department</span></span>  
  
-   <span data-ttu-id="ddbd0-113">Moeda de destino</span><span class="sxs-lookup"><span data-stu-id="ddbd0-113">Destination Currency</span></span>  
  
-   <span data-ttu-id="ddbd0-114">Funcionário</span><span class="sxs-lookup"><span data-stu-id="ddbd0-114">Employee</span></span>  
  
-   <span data-ttu-id="ddbd0-115">painel Geografia do app&#39;s selecionado</span><span class="sxs-lookup"><span data-stu-id="ddbd0-115">Geography</span></span>  
  
-   <span data-ttu-id="ddbd0-116">Detalhes do pedido de vendas pela Internet</span><span class="sxs-lookup"><span data-stu-id="ddbd0-116">Internet Sales Order Details</span></span>  
  
-   <span data-ttu-id="ddbd0-117">Organização</span><span class="sxs-lookup"><span data-stu-id="ddbd0-117">Organization</span></span>  
  
-   <span data-ttu-id="ddbd0-118">Produto</span><span class="sxs-lookup"><span data-stu-id="ddbd0-118">Product</span></span>  
  
-   <span data-ttu-id="ddbd0-119">Promoção</span><span class="sxs-lookup"><span data-stu-id="ddbd0-119">Promotion</span></span>  
  
-   <span data-ttu-id="ddbd0-120">Detalhes do pedido de vendas do revendedor</span><span class="sxs-lookup"><span data-stu-id="ddbd0-120">Reseller Sales Order Details</span></span>  
  
-   <span data-ttu-id="ddbd0-121">Revendedor</span><span class="sxs-lookup"><span data-stu-id="ddbd0-121">Reseller</span></span>  
  
-   <span data-ttu-id="ddbd0-122">Canal de vendas</span><span class="sxs-lookup"><span data-stu-id="ddbd0-122">Sales Channel</span></span>  
  
-   <span data-ttu-id="ddbd0-123">Motivo de vendas</span><span class="sxs-lookup"><span data-stu-id="ddbd0-123">Sales Reason</span></span>  
  
-   <span data-ttu-id="ddbd0-124">Detalhes do resumo do pedido de vendas</span><span class="sxs-lookup"><span data-stu-id="ddbd0-124">Sales Summary Order Details</span></span>  
  
-   <span data-ttu-id="ddbd0-125">Sales Territory</span><span class="sxs-lookup"><span data-stu-id="ddbd0-125">Sales Territory</span></span>  
  
-   <span data-ttu-id="ddbd0-126">Cenário</span><span class="sxs-lookup"><span data-stu-id="ddbd0-126">Scenario</span></span>  
  
-   <span data-ttu-id="ddbd0-127">Moeda de origem</span><span class="sxs-lookup"><span data-stu-id="ddbd0-127">Source Currency</span></span>  
  
 <span data-ttu-id="ddbd0-128">Cada um dos modelos padrão dá suporte a atributos que você pode escolher para serem incluídos na dimensão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-128">Each of the standard templates supports attributes that you can choose to include in the dimension.</span></span> <span data-ttu-id="ddbd0-129">Você também pode adicionar seus próprios arquivos de modelo a dimensões que geralmente são usadas com seus dados.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-129">You can also add your own template files for dimensions that are commonly used with your data.</span></span> <span data-ttu-id="ddbd0-130">Os modelos de dimensão ficam na seguinte pasta:</span><span class="sxs-lookup"><span data-stu-id="ddbd0-130">The dimension templates are located in the following folder:</span></span>  
  
 `C:\Program Files\Microsoft SQL Server\100\Tools\Templates\olap\1033\Dimension Templates`  
  
 <span data-ttu-id="ddbd0-131">Você pode usar o Designer de Dimensão depois de concluir o Assistente para Dimensões para adicionar, remover, e configurar atributos e hierarquias na dimensão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-131">You can use Dimension Designer after you complete the Dimension Wizard to add, remove, and configure attributes and hierarchies in the dimension.</span></span>  
  
 <span data-ttu-id="ddbd0-132">Quando você estiver criando uma dimensão que não seja de tempo sem usar uma fonte de dados, o Assistente para Dimensões o orientará durante as etapas de especificação do tipo de dimensão, identificando o atributo de chave, com dimensão de alteração lenta.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-132">When you are creating a non-time dimension without using a data source, the Dimension Wizard guides you through the steps of specifying the dimension type, and identifying the key attribute and slowly changing dimensions.</span></span>  
  
## <a name="specify-dimension-type"></a><span data-ttu-id="ddbd0-133">Especificar tipo de dimensão</span><span class="sxs-lookup"><span data-stu-id="ddbd0-133">Specify Dimension Type</span></span>  
 <span data-ttu-id="ddbd0-134">Na página **Especificar Tipo de Dimensão** do Assistente para Dimensões, você pode especificar o tipo de dimensão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-134">On the **Specify Dimension Type** page of the Dimension Wizard, you can specify the dimension type.</span></span> <span data-ttu-id="ddbd0-135">Se você estiver criando a dimensão com base em um modelo, o tipo de dimensão será definido para você.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-135">If you are building the dimension based on a template, the dimension type is defined for you.</span></span> <span data-ttu-id="ddbd0-136">Nessa página, você também pode selecionar atributos padrão para o tipo de dimensão especificado, se houver algum disponível.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-136">On this page, you can also select standard attributes for the specified dimension type if any are available.</span></span>  
  
 <span data-ttu-id="ddbd0-137">Se você selecionou um modelo que corresponde a um tipo de dimensão, essa página será populada com as opções do tipo de dimensão em questão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-137">If you selected a template that corresponds to a dimension type, this page is populated with the options for that dimension type.</span></span> <span data-ttu-id="ddbd0-138">Se você não selecionar um modelo, ou se não houver nenhum tipo de dimensão correspondente, o tipo de dimensão padrão será **Regular**.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-138">If you did not select a template, or if there is no corresponding dimension type, the default dimension type is **Regular**.</span></span> <span data-ttu-id="ddbd0-139">Se um tipo de dimensão não estiver selecionado, selecione o tipo mais apropriado para a dimensão que você está criando.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-139">If a dimension type is not already selected, select the most appropriate type for the dimension that you are creating.</span></span> <span data-ttu-id="ddbd0-140">Se nenhum tipo apropriado estiver listado para **Tipo de dimensão**, use **Regular**.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-140">If no appropriate type is listed for **Dimension type**, use **Regular**.</span></span>  
  
 <span data-ttu-id="ddbd0-141">Quando você seleciona um tipo de dimensão, o assistente lista os tipos de atributo que se aplicam a esta dimensão em **Atributos de dimensão**.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-141">When you select a dimension type, the wizard lists the attribute types that apply to this dimension under **Dimension attributes**.</span></span> <span data-ttu-id="ddbd0-142">Para selecionar um tipo de atributo, marque a caixa de seleção **Incluir** próximo ao tipo de atributo e digite o nome para o atributo em **Atributo de Dimensão**.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-142">To select an attribute type, select the **Include** check box next to the attribute type, and type the name for the attribute under **Dimension Attribute**.</span></span> <span data-ttu-id="ddbd0-143">O nome padrão é igual ao **Tipo de Atributo**.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-143">The default name is the same as **Attribute Type**.</span></span>  
  
## <a name="identify-key-attribute-and-changing-dimensions"></a><span data-ttu-id="ddbd0-144">Identificar Atributo de Chave e dimensões variáveis</span><span class="sxs-lookup"><span data-stu-id="ddbd0-144">Identify Key Attribute and Changing Dimensions</span></span>  
 <span data-ttu-id="ddbd0-145">Na página **Especificar Chave e Tipo de Dimensão** , selecione o atributo que você quer que seja o atributo de chave para a dimensão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-145">On the **Specify Dimension Key and Type** page, select the attribute that you want to be the key attribute for the dimension.</span></span> <span data-ttu-id="ddbd0-146">O atributo de chave corresponde normalmente à coluna de chave primária na tabela principal de dimensão e normalmente cria índices dos membros folha da dimensão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-146">The key attribute typically corresponds to the primary key column in the main dimension table, and it typically indexes the leaf members of the dimension.</span></span>  
  
 <span data-ttu-id="ddbd0-147">Se você selecionou um modelo, e um atributo de chave está definido no modelo, esse atributo será o atributo de chave padrão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-147">If you selected a template, and a key attribute is defined in the template, that attribute is the default key attribute.</span></span> <span data-ttu-id="ddbd0-148">Se você selecionou um modelo, mas nenhum atributo de chave está definido no modelo, o padrão será o primeiro atributo da lista.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-148">If you selected a template but no key attribute is defined in the template, the default is the first attribute in the list.</span></span> <span data-ttu-id="ddbd0-149">A lista contém todos os atributos que você selecionou na página **Especificar Tipo de Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="ddbd0-149">The list contains all the attributes that you selected on the **Specify Dimension Type** page.</span></span> <span data-ttu-id="ddbd0-150">Você pode selecionar qualquer um dos atributos selecionados na página **Especificar Tipo de Dimensão** para ser o atributo de chave.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-150">You can select any one of the attributes that you selected on the **Specify Dimension Type** page to be the key attribute.</span></span> <span data-ttu-id="ddbd0-151">Se você não selecionou nenhum atributo, o assistente criará um atributo de chave automaticamente e o nomeará concatenando o nome e a ID da dimensão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-151">If you did not select any attributes, the wizard automatically creates a key attribute and names it by concatenating the dimension name and "ID".</span></span>  
  
 <span data-ttu-id="ddbd0-152">Finalmente, especifique se essa dimensão é uma dimensão variável.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-152">Finally, specify whether this dimension is a changing dimension.</span></span> <span data-ttu-id="ddbd0-153">Com o tempo, membros em uma dimensão variável são movidos com o tempo para locais diferentes na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-153">Members in a changing dimension move over time to different locations in the hierarchy.</span></span> <span data-ttu-id="ddbd0-154">O assistente gera colunas adicionais e cria atributos que correspondem a essas colunas.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-154">The wizard generates additional columns and creates attributes that correspond to those columns.</span></span> <span data-ttu-id="ddbd0-155">Essas colunas permitirão que os usuários consultem a dimensão de forma a influenciar na alteração.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-155">These columns will let users query the dimension in such a way as to factor in the change.</span></span> <span data-ttu-id="ddbd0-156">Qualquer pacote que for criado depois com o Assistente de Geração de Esquema vai gerenciar chaves substitutas com base em características de dimensão de alteração lenta da dimensão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-156">Any packages that you subsequently create with the Schema Generation Wizard manage surrogate keys based on slowly changing dimension characteristics of the dimension.</span></span>  
  
 <span data-ttu-id="ddbd0-157">Quando você marcar a caixa de seleção **Esta é uma dimensão variável** , o Assistente para Dimensões definirá os atributos indicados na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="ddbd0-157">When you select the **This is a changing dimension** check box, the Dimension Wizard defines the attributes indicated in the following table:</span></span>  
  
|<span data-ttu-id="ddbd0-158">Atributo</span><span class="sxs-lookup"><span data-stu-id="ddbd0-158">Attribute</span></span>|<span data-ttu-id="ddbd0-159">Type</span><span class="sxs-lookup"><span data-stu-id="ddbd0-159">Type</span></span>|  
|---------------|----------|  
|<span data-ttu-id="ddbd0-160">SCD OriginalID</span><span class="sxs-lookup"><span data-stu-id="ddbd0-160">SCD OriginalID</span></span>|<span data-ttu-id="ddbd0-161">SCDOriginalID</span><span class="sxs-lookup"><span data-stu-id="ddbd0-161">SCDOriginalID</span></span>|  
|<span data-ttu-id="ddbd0-162">Data de Término da SCD</span><span class="sxs-lookup"><span data-stu-id="ddbd0-162">SCD End Date</span></span>|<span data-ttu-id="ddbd0-163">SCDEndDate</span><span class="sxs-lookup"><span data-stu-id="ddbd0-163">SCDEndDate</span></span>|  
|<span data-ttu-id="ddbd0-164">Data de Início da SCD</span><span class="sxs-lookup"><span data-stu-id="ddbd0-164">SCD Start Date</span></span>|<span data-ttu-id="ddbd0-165">SCDStartDate</span><span class="sxs-lookup"><span data-stu-id="ddbd0-165">SCDStartDate</span></span>|  
|<span data-ttu-id="ddbd0-166">Status da SCD</span><span class="sxs-lookup"><span data-stu-id="ddbd0-166">SCD Status</span></span>|<span data-ttu-id="ddbd0-167">SCDStatus</span><span class="sxs-lookup"><span data-stu-id="ddbd0-167">SCDStatus</span></span>|  
  
 <span data-ttu-id="ddbd0-168">Por padrão, a caixa de seleção **Esta é uma dimensão variável** ficará marcada se você usar um modelo que tenha esses atributos de dimensão de alteração lenta definidos.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-168">By default, the **This is a changing dimension** check box is selected if you use a template that has these slowly changing dimension attributes defined.</span></span> <span data-ttu-id="ddbd0-169">Se você desmarcar a caixa de seleção, os atributos de dimensão de alteração lenta serão removidos da dimensão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-169">If you clear the check box, the slowly changing dimension attributes are removed from the dimension.</span></span>  
  
 <span data-ttu-id="ddbd0-170">Você pode usar o Designer de Dimensão para configurar as propriedades para uma dimensão de alteração lenta.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-170">You can use Dimension Designer to configure properties for a slowly changing dimension.</span></span>  
  
## <a name="completing-the-dimension-wizard"></a><span data-ttu-id="ddbd0-171">Concluindo o Assistente para Dimensões</span><span class="sxs-lookup"><span data-stu-id="ddbd0-171">Completing the Dimension Wizard</span></span>  
 <span data-ttu-id="ddbd0-172">Na página **Concluindo o Assistente** , digite um nome para a nova dimensão e veja a estrutura da dimensão.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-172">On the **Completing the Wizard** page, type a name for the new dimension and view the dimension structure.</span></span> <span data-ttu-id="ddbd0-173">Marque a caixa de seleção **Gerar esquema agora** para iniciar o Assistente de Geração de Esquema depois que você clicar em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-173">Select the **Generate schema now** check box to start the Schema Generation Wizard after you click **Finish**.</span></span> <span data-ttu-id="ddbd0-174">Na maioria dos casos, você não deve marcar esta caixa de seleção se planejar criar outros objetos.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-174">In most cases, you should not select this check box if you plan to create additional objects.</span></span> <span data-ttu-id="ddbd0-175">Se você não marcar essa caixa de seleção, poderá usar o Designer de Dimensão para gerar o esquema posteriormente.</span><span class="sxs-lookup"><span data-stu-id="ddbd0-175">If you do not select this check box, you can use Dimension Designer to generate the schema later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddbd0-176">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ddbd0-176">See Also</span></span>  
 <span data-ttu-id="ddbd0-177">[Criar uma dimensão de tempo gerando uma tabela de tempo](create-a-time-dimension-by-generating-a-time-table.md) </span><span class="sxs-lookup"><span data-stu-id="ddbd0-177">[Create a Time Dimension by Generating a Time Table](create-a-time-dimension-by-generating-a-time-table.md) </span></span>  
 [<span data-ttu-id="ddbd0-178">Criar uma dimensão de tempo ao gerar uma tabela de tempo</span><span class="sxs-lookup"><span data-stu-id="ddbd0-178">Create a Time Dimension by Generating a Time Table</span></span>](create-a-time-dimension-by-generating-a-time-table.md)  
  
  
