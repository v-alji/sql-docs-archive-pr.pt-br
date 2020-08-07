---
title: Definindo uma dimensão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 112696db-3838-4b50-91bd-d2ce5fa04ee5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2eb7a695ffc2c0588396a4a9ea655983c26cc719
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568836"
---
# <a name="defining-a-dimension"></a><span data-ttu-id="9e7a8-102">Definindo uma dimensão</span><span class="sxs-lookup"><span data-stu-id="9e7a8-102">Defining a Dimension</span></span>
  <span data-ttu-id="9e7a8-103">Na tarefa a seguir, você usará o Assistente para Dimensões para criar uma dimensão Data.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-103">In the following task, you will use the Dimension Wizard to build a Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e7a8-104">Esta lição requer a conclusão de todos os procedimentos da Lição 1.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-104">This lesson requires that you have completed all the procedures in Lesson 1.</span></span>  
  
### <a name="to-define-a-dimension"></a><span data-ttu-id="9e7a8-105">Para definir uma dimensão</span><span class="sxs-lookup"><span data-stu-id="9e7a8-105">To define a dimension</span></span>  
  
1.  <span data-ttu-id="9e7a8-106">No Gerenciador de Soluções (no lado direito da janela Microsoft Visual Studio), clique com o botão direito do mouse em **Dimensões**e clique em **Nova Dimensão**.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-106">In Solution Explorer (on the right side of Microsoft Visual Studio), right-click **Dimensions**, and then click **New Dimension**.</span></span> <span data-ttu-id="9e7a8-107">O Assistente para Dimensões é exibido.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-107">The Dimension Wizard appears.</span></span>  
  
2.  <span data-ttu-id="9e7a8-108">Na página **Bem-vindo ao Assistente para Dimensões** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-108">On the **Welcome to the Dimension Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="9e7a8-109">Na página **Selecionar Método de Criação** , verifique se a opção **Usar uma tabela existente** está selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-109">On the **Select Creation Method** page, verify that the **Use an existing table** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="9e7a8-110">Na página **Especificar Informações da Fonte** , verifique se a exibição da fonte de dados **Adventure Works DW 2012** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-110">On the **Specify Source Information** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="9e7a8-111">Na lista **Tabela principal** , selecione **Date**.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-111">In the **Main table** list, select **Date**.</span></span>  
  
6.  <span data-ttu-id="9e7a8-112">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-112">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="9e7a8-113">Na página **Selecionar Atributos de Dimensão** , marque as caixas de seleção dos seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="9e7a8-113">On the **Select Dimension Attributes** page, select the check boxes next to the following attributes:</span></span>  
  
    -   <span data-ttu-id="9e7a8-114">**Chave de Data**</span><span class="sxs-lookup"><span data-stu-id="9e7a8-114">**Date Key**</span></span>  
  
    -   <span data-ttu-id="9e7a8-115">**Chave Alternativa de Data Completa**</span><span class="sxs-lookup"><span data-stu-id="9e7a8-115">**Full Date Alternate Key**</span></span>  
  
    -   <span data-ttu-id="9e7a8-116">**Nome do Mês em Inglês**</span><span class="sxs-lookup"><span data-stu-id="9e7a8-116">**English Month Name**</span></span>  
  
    -   <span data-ttu-id="9e7a8-117">**Trimestre do calendário**</span><span class="sxs-lookup"><span data-stu-id="9e7a8-117">**Calendar Quarter**</span></span>  
  
    -   <span data-ttu-id="9e7a8-118">**Ano civil**</span><span class="sxs-lookup"><span data-stu-id="9e7a8-118">**Calendar Year**</span></span>  
  
    -   <span data-ttu-id="9e7a8-119">**Calendar Semester**</span><span class="sxs-lookup"><span data-stu-id="9e7a8-119">**Calendar Semester**</span></span>  
  
8.  <span data-ttu-id="9e7a8-120">Altere a configuração da coluna **Tipo de Atributo** do atributo **Full Date Alternate Key** de **Regular** para **Date**.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-120">Change the setting of the **Full Date Alternate Key** attribute's **Attribute Type** column from **Regular** to **Date**.</span></span> <span data-ttu-id="9e7a8-121">Para fazer isso, clique em **Regular** na coluna **Tipo de Atributo** .</span><span class="sxs-lookup"><span data-stu-id="9e7a8-121">To do this, click **Regular** in the **Attribute Type** column.</span></span> <span data-ttu-id="9e7a8-122">Em seguida, clique na seta para expandir as opções.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-122">Then click the arrow to expand the options.</span></span> <span data-ttu-id="9e7a8-123">Em seguida, clique em data do calendário de **Data**  >  **Calendar**  >  **Date**.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-123">Next, click **Date** > **Calendar** > **Date**.</span></span> <span data-ttu-id="9e7a8-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-124">Click **OK**.</span></span> <span data-ttu-id="9e7a8-125">Repita essas etapas para alterar o tipo de atributo dos atributos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9e7a8-125">Repeat these steps to change the attribute type of the attributes as follows:</span></span>  
  
    -   <span data-ttu-id="9e7a8-126">**English Month Name** para **Month**</span><span class="sxs-lookup"><span data-stu-id="9e7a8-126">**English Month Name** to **Month**</span></span>  
  
    -   <span data-ttu-id="9e7a8-127">**Calendar Quarter** para **Quarter**</span><span class="sxs-lookup"><span data-stu-id="9e7a8-127">**Calendar Quarter** to **Quarter**</span></span>  
  
    -   <span data-ttu-id="9e7a8-128">**Ano Civil** para **Ano**</span><span class="sxs-lookup"><span data-stu-id="9e7a8-128">**Calendar Year** to **Year**</span></span>  
  
    -   <span data-ttu-id="9e7a8-129">**Calendar Semester** para **Half Year**</span><span class="sxs-lookup"><span data-stu-id="9e7a8-129">**Calendar Semester** to **Half Year**</span></span>  
  
9. <span data-ttu-id="9e7a8-130">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-130">Click **Next**.</span></span>  
  
10. <span data-ttu-id="9e7a8-131">Na página **Concluindo o Assistente** , no painel Visualização, é possível ver a dimensão **Data** e seus atributos.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-131">On the **Completing the Wizard** page, in the Preview pane, you can see the **Date** dimension and its attributes.</span></span>  
  
11. <span data-ttu-id="9e7a8-132">Clique em **Concluir** para finalizar o assistente.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-132">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="9e7a8-133">No Gerenciador de Soluções, no projeto Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , a dimensão Data é exibida na pasta **Dimensões** .</span><span class="sxs-lookup"><span data-stu-id="9e7a8-133">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the Date dimension appears in the **Dimensions** folder.</span></span> <span data-ttu-id="9e7a8-134">No centro do ambiente de desenvolvimento, o Designer de Dimensão exibe a dimensão Data.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-134">In the center of the development environment, Dimension Designer displays the Date dimension.</span></span>  
  
12. <span data-ttu-id="9e7a8-135">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-135">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9e7a8-136">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="9e7a8-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9e7a8-137">Definindo um cubo</span><span class="sxs-lookup"><span data-stu-id="9e7a8-137">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="9e7a8-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9e7a8-138">See Also</span></span>  
 <span data-ttu-id="9e7a8-139">[Dimensões em modelos multidimensionais](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="9e7a8-139">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="9e7a8-140">[Criar uma dimensão usando uma tabela existente](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span><span class="sxs-lookup"><span data-stu-id="9e7a8-140">[Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span></span>  
 [<span data-ttu-id="9e7a8-141">Criar uma dimensão usando o Assistente para Dimensões</span><span class="sxs-lookup"><span data-stu-id="9e7a8-141">Create a Dimension Using the Dimension Wizard</span></span>](multidimensional-models/create-a-dimension-using-the-dimension-wizard.md)  
  
  
