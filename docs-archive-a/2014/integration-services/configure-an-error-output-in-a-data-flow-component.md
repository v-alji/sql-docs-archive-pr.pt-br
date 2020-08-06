---
title: Configurar uma saída de erro em um componente de fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- errors [Integration Services], data flow components
- components [Integration Services], data flow
- error outputs [Integration Services]
ms.assetid: 53d7eeea-927d-4b45-8ea9-084e65ad5390
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebd44383e27daa465576bb056a67f6dacad87b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685244"
---
# <a name="configure-an-error-output-in-a-data-flow-component"></a><span data-ttu-id="fe4d2-102">Configurar uma saída de erro em um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="fe4d2-102">Configure an Error Output in a Data Flow Component</span></span>
  <span data-ttu-id="fe4d2-103">Muitos componentes de fluxo de dados dão suporte a saídas de erro e, dependendo do componente, o [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer fornece diferentes modos de configurar uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-103">Many data flow components support error outputs, and depending on the component, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides different ways to configure an error output.</span></span> <span data-ttu-id="fe4d2-104">Além de configurar uma saída de erro, você pode configurar também as colunas de uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-104">In addition to configuring an error output, you can also configure the columns of an error output.</span></span> <span data-ttu-id="fe4d2-105">Isto inclui a configuração das colunas **ErrorCode** e **ErrorColumn** que são adicionadas pelo componente.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-105">This includes configuring the **ErrorCode** and **ErrorColumn** columns that are added by the component.</span></span>  
  
## <a name="configuring-an-error-output"></a><span data-ttu-id="fe4d2-106">Configurando uma saída de erro</span><span class="sxs-lookup"><span data-stu-id="fe4d2-106">Configuring an Error Output</span></span>  
 <span data-ttu-id="fe4d2-107">Para configurar uma saída de erro, você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="fe4d2-107">To configure an error output, you have two options:</span></span>  
  
-   <span data-ttu-id="fe4d2-108">Use a caixa de diálogo **Configurar Saída de Erro** .</span><span class="sxs-lookup"><span data-stu-id="fe4d2-108">Use the **Configure Error Output** dialog box.</span></span> <span data-ttu-id="fe4d2-109">Você pode usar esta caixa de diálogo para configurar uma saída de erro em qualquer componente de fluxo de dados que ofereça suporte a saídas de erro.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-109">You can use this dialog box to configure an error output on any data flow component that supports an error output.</span></span>  
  
-   <span data-ttu-id="fe4d2-110">Use a caixa de diálogo do editor para o componente.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-110">Use the editor dialog box for the component.</span></span> <span data-ttu-id="fe4d2-111">Alguns componentes permitem que você configure saídas de erro diretamente na caixa de diálogo do editor.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-111">Some components let you configure error outputs directly from their editor dialog box.</span></span> <span data-ttu-id="fe4d2-112">Entretanto, você não pode configurar saídas de erros da caixa de diálogo do editor para a origem do ADO NET, a transformação de Importar Coluna e do Comando OLE DB ou para o destino do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-112">However, you cannot configure error outputs from the editor dialog box for the ADO NET source, the Import Column transformation, the OLE DB Command transformation, or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact destination.</span></span>  
  
 <span data-ttu-id="fe4d2-113">Os procedimentos a seguir descrevem como usar estas caixas de diálogo para configurar saídas de erro.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-113">The following procedures describe how to use these dialog boxes to configure error outputs.</span></span>  
  
#### <a name="to-configure-an-error-output-using-the-configure-error-output-dialog-box"></a><span data-ttu-id="fe4d2-114">Para configurar uma saída de erro que usa a caixa de diálogo Configurar Saída de Erro</span><span class="sxs-lookup"><span data-stu-id="fe4d2-114">To configure an error output using the Configure Error Output dialog box</span></span>  
  
1.  <span data-ttu-id="fe4d2-115">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="fe4d2-116">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="fe4d2-117">No [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, clique na guia **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="fe4d2-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="fe4d2-118">Arraste a saída de erro, representada pela seta vermelha, do componente que é a fonte dos erros para outro componente no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-118">Drag the error output, represented by the red arrow, from the component that is the source of the errors to another component in the data flow.</span></span>  
  
5.  <span data-ttu-id="fe4d2-119">Na caixa de diálogo **Configurar Saída de Erro** , selecione uma ação nas colunas **Erro** e **Truncamento** para cada coluna da entrada de componente.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-119">In the **Configure Error Output** dialog box, select an action in the **Error** and **Truncation** columns for each column in the component input.</span></span>  
  
6.  <span data-ttu-id="fe4d2-120">Para salvar o pacote atualizado, no menu **Arquivo** , clique em **Salvar Itens Selecionados**.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-120">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
#### <a name="to-add-an-error-output-using-the-editor-dialog-box-for-the-component"></a><span data-ttu-id="fe4d2-121">Para adicionar uma saída de erro que usa a caixa de diálogo do editor para o componente</span><span class="sxs-lookup"><span data-stu-id="fe4d2-121">To add an error output using the editor dialog box for the component</span></span>  
  
1.  <span data-ttu-id="fe4d2-122">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="fe4d2-123">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="fe4d2-124">No [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, clique na guia **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="fe4d2-124">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="fe4d2-125">Clique duas vezes nos componentes de fluxo de dados em que você deseja configurar uma saída de erro e, dependendo do componente, siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="fe4d2-125">Double-click the data flow components in which you want to configure an error output and, depending on the component, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="fe4d2-126">Clique em **Configurar Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-126">Click **Configure Error Output**.</span></span>  
  
    -   <span data-ttu-id="fe4d2-127">Clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-127">Click **Error Output**.</span></span>  
  
5.  <span data-ttu-id="fe4d2-128">Defina a opção **Erro** para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-128">Set the **Error** option for each column.</span></span>  
  
6.  <span data-ttu-id="fe4d2-129">Defina a opção **Truncamento** para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-129">Set the **Truncation** option for each column.</span></span>  
  
7.  <span data-ttu-id="fe4d2-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-130">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="fe4d2-131">Para salvar o pacote atualizado, no menu **Arquivo** , clique em **Salvar Itens Selecionados**.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-131">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="configuring-error-output-columns"></a><span data-ttu-id="fe4d2-132">Configurando colunas de saída de erro</span><span class="sxs-lookup"><span data-stu-id="fe4d2-132">Configuring Error Output Columns</span></span>  
 <span data-ttu-id="fe4d2-133">Para configurar colunas de saída de erro, você deve usar a guia **Propriedades de Entrada e Saída** na caixa de diálogo **Editor Avançado** .</span><span class="sxs-lookup"><span data-stu-id="fe4d2-133">To configure the error output columns, you have to use the **Input and Output Properties** tab of the **Advanced Editor** dialog box.</span></span>  
  
#### <a name="to-configure-error-output-columns"></a><span data-ttu-id="fe4d2-134">Para configurar colunas de saída de erro</span><span class="sxs-lookup"><span data-stu-id="fe4d2-134">To configure error output columns</span></span>  
  
1.  <span data-ttu-id="fe4d2-135">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-135">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="fe4d2-136">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-136">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="fe4d2-137">No [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, clique na guia **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="fe4d2-137">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="fe4d2-138">Clique com o botão direito do mouse no componente cujas colunas de saída de erro você deseja configurar e clique em **Mostrar Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-138">Right-click the component whose error output columns you want to configure and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="fe4d2-139">Clique na guia **Propriedades de Entrada e Saída**, expanda **Saída de Erro do \<component name>** e, então, expanda **Colunas de Saída**.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-139">Click the **Input and Output Properties** tab and expand **\<component name> Error Output** and then expand **Output Columns**.</span></span>  
  
6.  <span data-ttu-id="fe4d2-140">Clique em uma coluna e atualize suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-140">Click a column and update its properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fe4d2-141">A lista de colunas inclui as colunas na entrada do componente, as colunas **ErrorCode** e **ErrorColumn** adicionadas pelas saídas de erros anteriores e as colunas **ErrorCode** e **ErrorColumn** adicionadas por este componente.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-141">The list of columns includes the columns in the component input, the **ErrorCode** and **ErrorColumn** columns added by previous error outputs, and the **ErrorCode** and **ErrorColumn** columns added by this component.</span></span>  
  
7.  <span data-ttu-id="fe4d2-142">Clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="fe4d2-142">Click **OK.**</span></span>  
  
8.  <span data-ttu-id="fe4d2-143">Para salvar o pacote atualizado, no menu **Arquivo** , clique em **Salvar Itens Selecionados**.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-143">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe4d2-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fe4d2-144">See Also</span></span>  
 [<span data-ttu-id="fe4d2-145">Tratamento de erro em dados</span><span class="sxs-lookup"><span data-stu-id="fe4d2-145">Error Handling in Data</span></span>](data-flow/error-handling-in-data.md)  
  
  
