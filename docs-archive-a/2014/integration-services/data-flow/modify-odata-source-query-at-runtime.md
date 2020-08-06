---
title: Modificar consulta de origem OData em tempo de execução | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bcbba7f4-6e5d-46e6-a73a-3f17d3ff376a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b3dbc4d27f2d11537a9d66980ef6ca59b80811b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685218"
---
# <a name="modify-odata-source-query-at-runtime"></a><span data-ttu-id="22097-102">Modifique a consulta de origem do OData em runtime</span><span class="sxs-lookup"><span data-stu-id="22097-102">Modify OData Source Query at Runtime</span></span>
  <span data-ttu-id="22097-103">Você pode alterar a consulta de OData Source em runtime adicionando uma expressão à propriedade **[Origem OData].[Consulta]** da Tarefa de Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="22097-103">You can modify the OData Source query at runtime by adding an expression to the **[OData Source].[Query]** property of the Data Flow task.</span></span>  
  
 <span data-ttu-id="22097-104">Observe que as colunas devem permanecer iguais às que foram usadas em tempo de design; caso contrário, você receberá um erro quando o pacote for executado.</span><span class="sxs-lookup"><span data-stu-id="22097-104">Note that the columns must remain the same as what was used at design time; otherwise you will get an error when the package is executed.</span></span> <span data-ttu-id="22097-105">Certifique-se de especificar as mesmas colunas (na mesma ordem) ao usar a opção de consulta de $select.</span><span class="sxs-lookup"><span data-stu-id="22097-105">Be sure to specify the same columns (in the same order) when using the $select query option.</span></span> <span data-ttu-id="22097-106">Uma alternativa mais segura para usar a opção de $select é desmarcar as colunas que você não deseja diretamente na interface do usuário do componente de origem.</span><span class="sxs-lookup"><span data-stu-id="22097-106">A safer alternative to using the $select option is to deselect the columns you don't want directly from the Source Component UI.</span></span>  
  
 <span data-ttu-id="22097-107">Há algumas maneiras diferentes de definir dinamicamente o valor da consulta em runtime.</span><span class="sxs-lookup"><span data-stu-id="22097-107">There are a few different ways of dynamically setting the query value at runtime.</span></span> <span data-ttu-id="22097-108">A seguir estão alguns dos métodos mais comuns.</span><span class="sxs-lookup"><span data-stu-id="22097-108">Below are some of the more common methods.</span></span>  
  
## <a name="exposing-the-query-as-a-parameter"></a><span data-ttu-id="22097-109">Expor a consulta como um parâmetro</span><span class="sxs-lookup"><span data-stu-id="22097-109">Exposing the Query as a Parameter</span></span>  
 <span data-ttu-id="22097-110">O procedimento a seguir tem etapas para expor a consulta usada por um componente de origem OData como um parâmetro ao pacote.</span><span class="sxs-lookup"><span data-stu-id="22097-110">The following procedure has steps to expose query used by an OData Source component as a parameter to the package.</span></span>  
  
1.  <span data-ttu-id="22097-111">Clique com o botão direito do mouse em **Tarefa de Fluxo de Dados** e selecione a opção **Parametrizar...** .</span><span class="sxs-lookup"><span data-stu-id="22097-111">Right click on the **Data Flow task** and select the **Parameterize...** option.</span></span>  
  
2.  <span data-ttu-id="22097-112">Na caixa de diálogo **Parametrizar**, selecione **[\<Name of the OData Source Component>].[Consulta]** para **Propriedade**.</span><span class="sxs-lookup"><span data-stu-id="22097-112">In the **Parameterize** dialog, select **[\<Name of the OData Source Component>].[Query]** for **Property**.</span></span>  
  
3.  <span data-ttu-id="22097-113">Escolha se deseja **criar novo parâmetro** ou **usar um parâmetro existente**.</span><span class="sxs-lookup"><span data-stu-id="22097-113">Choose whether to **create new parameter** or **use an existing parameter**.</span></span>  
  
4.  <span data-ttu-id="22097-114">Se você selecionar **Criar novo parâmetro**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22097-114">If you select **Create new parameter**, do the following:</span></span>  
  
    1.  <span data-ttu-id="22097-115">Insira um **nome** e **descrição** para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="22097-115">Enter **name** and **description** for the parameter.</span></span>  
  
    2.  <span data-ttu-id="22097-116">Especifique o **valor** padrão para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="22097-116">Specify default **value** for the parameter.</span></span>  
  
    3.  <span data-ttu-id="22097-117">Especifique o **escopo** (**pacote** ou **projeto**) para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="22097-117">Specify the **scope** (**package** or **project**) for the parameter.</span></span>  
  
    4.  <span data-ttu-id="22097-118">Especifique se o parâmetro é ou não **obrigatório**</span><span class="sxs-lookup"><span data-stu-id="22097-118">Specify whether the parameter is **required** or not</span></span>  
  
5.  <span data-ttu-id="22097-119">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="22097-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="using-an-expression"></a><span data-ttu-id="22097-120">Usando uma expressão</span><span class="sxs-lookup"><span data-stu-id="22097-120">Using an Expression</span></span>  
 <span data-ttu-id="22097-121">Este método será útil quando você desejar construir dinamicamente a cadeia de caracteres de consulta em runtime.</span><span class="sxs-lookup"><span data-stu-id="22097-121">This method is useful when you want to dynamically construct query string at runtime.</span></span> <span data-ttu-id="22097-122">Neste exemplo, a variável MaxRows será definida com outros meios (script, parâmetro, etc.).</span><span class="sxs-lookup"><span data-stu-id="22097-122">In this example, MaxRows variable will be set through other means (script, parameter, etc).</span></span>  
  
1.  <span data-ttu-id="22097-123">Selecione a **Tarefa de Fluxo de Dados** que contém a sua **Fonte OData**.</span><span class="sxs-lookup"><span data-stu-id="22097-123">Select the **Data Flow Task** which contains your **OData Source**.</span></span>  
  
2.  <span data-ttu-id="22097-124">Na janela **Propriedades** , destaque a propriedade **Expressões** .</span><span class="sxs-lookup"><span data-stu-id="22097-124">In the **Properties** window, highlight the **Expressions** property.</span></span>  
  
3.  <span data-ttu-id="22097-125">Clique em... botão (reticências) para abrir o **Editor de expressões de propriedade**.</span><span class="sxs-lookup"><span data-stu-id="22097-125">Click the ... (ellipses) button to bring up the **Property Expressions Editor**.</span></span>  
  
4.  <span data-ttu-id="22097-126">Selecione a propriedade de **[Fonte do OData].[Consulta]** .</span><span class="sxs-lookup"><span data-stu-id="22097-126">Select the **[OData Source].[Query]** property.</span></span>  
  
5.  <span data-ttu-id="22097-127">Clique em... botão (reticências) da **expressão**.</span><span class="sxs-lookup"><span data-stu-id="22097-127">Click the ... (ellipses) button for **Expression**.</span></span>  
  
6.  <span data-ttu-id="22097-128">Insira a **expressão**.</span><span class="sxs-lookup"><span data-stu-id="22097-128">Enter the **expression**.</span></span>  
  
7.  <span data-ttu-id="22097-129">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="22097-129">Click **OK**.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="22097-130">Observe que ao usar essa abordagem você precisa garantir que os valores definidos sejam codificados corretamente no URL.</span><span class="sxs-lookup"><span data-stu-id="22097-130">Note that when using this approach you need to ensure that the values set are properly URL encoded.</span></span> <span data-ttu-id="22097-131">Ao receber valores de entrada do usuário (por exemplo, definindo valores de opção consulta individual de um parâmetro), certifique-se de que os valores sejam validados para impedir ataques potenciais do tipo injeção do SQL.</span><span class="sxs-lookup"><span data-stu-id="22097-131">When receiving values from user input (for example, setting individual query option values from a parameter), you must ensure that the values are validated to avoid potential SQL injection-type attacks.</span></span>  
  
  
