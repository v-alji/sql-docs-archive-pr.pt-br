---
title: Bibliotecas de classes de itens de relatório personalizados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, RDL
- RDL [Reporting Services], custom report items
ms.assetid: f18c5d8f-1d6b-4f0b-8657-c14896c2ce0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 60f8cf912eb6ff3f5080e9cf757df40f37e65079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569208"
---
# <a name="custom-report-item-class-libraries"></a><span data-ttu-id="c2e20-102">Bibliotecas de classes de itens de relatório personalizados</span><span class="sxs-lookup"><span data-stu-id="c2e20-102">Custom Report Item Class Libraries</span></span>
  <span data-ttu-id="c2e20-103">Os itens de relatórios personalizados usam classes do namespace `Microsoft.ReportDesigner`.</span><span class="sxs-lookup"><span data-stu-id="c2e20-103">Custom report items use classes from the `Microsoft.ReportDesigner` namespace.</span></span> <span data-ttu-id="c2e20-104">As classes usadas para implementar um item de relatório personalizado podem ser agrupadas em duas categorias principais: classes exclusivas destinadas a dar suporte à infraestrutura do item de relatório personalizado, e classes de wrapper gerenciado que encapsula a funcionalidade de elementos relevantes em linguagem RDL.</span><span class="sxs-lookup"><span data-stu-id="c2e20-104">The classes used to implement a custom report item can be grouped into two main categories: unique classes designed to support custom report item infrastructure, and managed wrapper classes that encapsulate the functionality of relevant Report Definition Language (RDL) elements.</span></span> <span data-ttu-id="c2e20-105">Para obter um exemplo de código sobre como usar essas classes, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="c2e20-105">For a code sample on how to use these classes, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-infrastructure-classes"></a><span data-ttu-id="c2e20-106">Classes de infraestrutura de itens de relatórios personalizados</span><span class="sxs-lookup"><span data-stu-id="c2e20-106">Custom Report Item Infrastructure Classes</span></span>  
 <span data-ttu-id="c2e20-107">As classes a seguir são usadas para implementar um item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-107">The following classes are used to implement a custom report item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2e20-108">As tabelas a seguir não são listagens completas; elas incluem apenas as propriedades e os métodos mais usados para cada classe.</span><span class="sxs-lookup"><span data-stu-id="c2e20-108">The following tables are not complete listings; they include only the most commonly used properties and methods for each class.</span></span>  
  
### <a name="microsoftreportdesignercustomreportitemdesigner"></a><span data-ttu-id="c2e20-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span><span class="sxs-lookup"><span data-stu-id="c2e20-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span></span>  
 <span data-ttu-id="c2e20-110">Esta é a principal classe de item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-110">This is the main custom report item class.</span></span> <span data-ttu-id="c2e20-111">A classe principal de sua implementação de item de relatório personalizado deve ser herdada dessa classe.</span><span class="sxs-lookup"><span data-stu-id="c2e20-111">The main class of your custom report item implementation must inherit from this class.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="c2e20-112">Propriedades públicas</span><span class="sxs-lookup"><span data-stu-id="c2e20-112">Public Properties</span></span>  
  
|||  
|-|-|  
|`Name`|<span data-ttu-id="c2e20-113">O nome do item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-113">The name of the custom report item.</span></span>|  
|`Type`|<span data-ttu-id="c2e20-114">O tipo do item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-114">The type of the custom report item.</span></span>|  
|`CustomData`|<span data-ttu-id="c2e20-115">Um objeto <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> que encapsula as propriedades de dados do item de relatório personalizado especificadas no momento da criação.</span><span class="sxs-lookup"><span data-stu-id="c2e20-115">A <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> object that encapsulates the custom report item data properties specified at design time.</span></span>|  
|`CustomProperties`|<span data-ttu-id="c2e20-116">Uma coleção de propriedades personalizadas do item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-116">A collection of custom properties for the custom report item.</span></span>|  
|`Height`|<span data-ttu-id="c2e20-117">A altura do controle do item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-117">The height of the custom report item control.</span></span>|  
|`Width`|<span data-ttu-id="c2e20-118">A largura do controle do item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-118">The width of the custom report item control.</span></span>|  
|`Report`|<span data-ttu-id="c2e20-119">Um contêiner das propriedades em nível de relatório, como a lista de conjuntos de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="c2e20-119">A container for the report-level properties, such as the list of datasets in the report.</span></span>|  
|`AltReportItem`|<span data-ttu-id="c2e20-120">O objeto de item de relatório alternativo, a ser usado onde o controle de item de relatório personalizado em tempo de execução não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="c2e20-120">The alternate report item object, to be used where the custom report item run-time control is not supported.</span></span>|  
|`Style`|<span data-ttu-id="c2e20-121">As propriedades de estilo do item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-121">The style properties for the custom report item.</span></span>|  
|`Adornment`|<span data-ttu-id="c2e20-122">Uma janela de adorno usada para a edição interativa do controle.</span><span class="sxs-lookup"><span data-stu-id="c2e20-122">An adornment window used for interactive editing of the control.</span></span>|  
|`Site`|<span data-ttu-id="c2e20-123">O `ISite` do componente.</span><span class="sxs-lookup"><span data-stu-id="c2e20-123">The `ISite` of the component.</span></span>|  
|`DesignerVerbCollection`|<span data-ttu-id="c2e20-124">Uma matriz de verbos personalizados do menu de atalho do controle.</span><span class="sxs-lookup"><span data-stu-id="c2e20-124">An array of custom verbs for the control's shortcut menu.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="c2e20-125">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="c2e20-125">Public Methods</span></span>  
  
|||  
|-|-|  
|`BeginEdit`|<span data-ttu-id="c2e20-126">Ativa a edição interativa do controle.</span><span class="sxs-lookup"><span data-stu-id="c2e20-126">Activates interactive editing for the control.</span></span>|  
|`DoDefaultAction`|<span data-ttu-id="c2e20-127">Chamado em resposta ao clique duplo ou pressionamento de Retornar no controle.</span><span class="sxs-lookup"><span data-stu-id="c2e20-127">Called in response to double-clicking or pressing Return on the control.</span></span>|  
|`EndEdit`|<span data-ttu-id="c2e20-128">Desativa a edição interativa do controle.</span><span class="sxs-lookup"><span data-stu-id="c2e20-128">Deactivates interactive editing for the control.</span></span>|  
|`GetService`|<span data-ttu-id="c2e20-129">Retorna um objeto que representa um serviço.</span><span class="sxs-lookup"><span data-stu-id="c2e20-129">Returns an object which represents a service.</span></span>|  
|`InitializeNewComponent`|<span data-ttu-id="c2e20-130">Chamado quando um novo item de relatório personalizado é criado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-130">Called when a new custom report item is created.</span></span>|  
|`Invalidate`|<span data-ttu-id="c2e20-131">Redesenha a superfície inteira do controle.</span><span class="sxs-lookup"><span data-stu-id="c2e20-131">Repaints the entire surface of the control.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragDrop`|<span data-ttu-id="c2e20-132">Chamado quando um objeto é arrastado para o controle.</span><span class="sxs-lookup"><span data-stu-id="c2e20-132">Called when an object is dragged onto the control.</span></span>|  
|`OnPaint`|<span data-ttu-id="c2e20-133">Chamado em resposta ao evento `Paint`.</span><span class="sxs-lookup"><span data-stu-id="c2e20-133">Called in response to the `Paint` event.</span></span>|  
  
### <a name="microsoftreportdesignercustomreportitemattribute"></a><span data-ttu-id="c2e20-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span><span class="sxs-lookup"><span data-stu-id="c2e20-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span></span>  
 <span data-ttu-id="c2e20-135">Este é o atributo usado para identificar o tipo do item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-135">This is the attribute used to identify the type of the custom report item.</span></span> <span data-ttu-id="c2e20-136">O nome deve corresponder ao valor do atributo <`Name`> do `ReportItem` elemento no arquivo de configuração Report Designer.</span><span class="sxs-lookup"><span data-stu-id="c2e20-136">The name must match the value of the <`Name`> attribute of the `ReportItem` element in the Report Designer configuration file.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="c2e20-137">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="c2e20-137">Public Methods</span></span>  
  
|||  
|-|-|  
|`CustomReportItemAttribute`|<span data-ttu-id="c2e20-138">Constrói o objeto CustomReportItemAttribute.</span><span class="sxs-lookup"><span data-stu-id="c2e20-138">Constructs the CustomReportItemAttribute object.</span></span>|  
  
### <a name="microsoftreportdesignerlocalizednameattribute"></a><span data-ttu-id="c2e20-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span><span class="sxs-lookup"><span data-stu-id="c2e20-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span></span>  
 <span data-ttu-id="c2e20-140">Este é o atributo usado para especificar o nome para exibição a ser usado para o designer de item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-140">This is the attribute used to specify display name to use for the custom report item designer.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="c2e20-141">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="c2e20-141">Public Methods</span></span>  
  
|||  
|-|-|  
|`LocalizedNameAttribute`|<span data-ttu-id="c2e20-142">Constrói o objeto LocalizedNameAttribute.</span><span class="sxs-lookup"><span data-stu-id="c2e20-142">Constructs the LocalizedNameAttribute object.</span></span>|  
  
### <a name="microsoftreportdesigneradornment"></a><span data-ttu-id="c2e20-143">Microsoft.ReportDesigner.Adornment</span><span class="sxs-lookup"><span data-stu-id="c2e20-143">Microsoft.ReportDesigner.Adornment</span></span>  
 <span data-ttu-id="c2e20-144">A classe `Adornment` é usada pelo componente de item de relatório personalizado em tempo de design para fornecer áreas fora do retângulo principal da superfície de design.</span><span class="sxs-lookup"><span data-stu-id="c2e20-144">The `Adornment` class is used by the custom report item design-time component to provide areas outside of the main rectangle of the design surface.</span></span> <span data-ttu-id="c2e20-145">Essas áreas podem tratar eventos de interface do usuário, tais como cliques de mouse e operações de arrastar e soltar.</span><span class="sxs-lookup"><span data-stu-id="c2e20-145">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="c2e20-146">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="c2e20-146">Public Methods</span></span>  
  
|||  
|-|-|  
|`OnShow`|<span data-ttu-id="c2e20-147">Chamado quando `Adornment` está ativado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-147">Called when the `Adornment` is activated.</span></span>|  
|`OnHide`|<span data-ttu-id="c2e20-148">Chamado quando `Adornment` está desativado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-148">Called when the `Adornment` is deactivated.</span></span>|  
|`Paint`|<span data-ttu-id="c2e20-149">Chamado em resposta ao evento `Paint`.</span><span class="sxs-lookup"><span data-stu-id="c2e20-149">Called in response to the `Paint` event.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragOver`<br /><br /> `OnDragLeave`<br /><br /> `OnDragDrop`|<span data-ttu-id="c2e20-150">Chamado quando um objeto é arrastado para o `Adornment`.</span><span class="sxs-lookup"><span data-stu-id="c2e20-150">Called when an object is dragged into the `Adornment`.</span></span>|  
  
### <a name="microsoftreportdesigneradornerservice"></a><span data-ttu-id="c2e20-151">Microsoft.ReportDesigner.AdornerService</span><span class="sxs-lookup"><span data-stu-id="c2e20-151">Microsoft.ReportDesigner.AdornerService</span></span>  
 <span data-ttu-id="c2e20-152">Esta classe é usada para fornecer uma coleção de serviços de exibição usados pelo item de relatório personalizado para dar suporte a objetos `Adornment` para o componente de item de relatório personalizado em tempo de design.</span><span class="sxs-lookup"><span data-stu-id="c2e20-152">This class is used to provide a collection of display services used by the custom report item to support `Adornment` objects for the custom report item design-time component.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="c2e20-153">Propriedades públicas</span><span class="sxs-lookup"><span data-stu-id="c2e20-153">Public Properties</span></span>  
  
|||  
|-|-|  
|`AdornerWindowBounds`|<span data-ttu-id="c2e20-154">Os limites da janela Adorno.</span><span class="sxs-lookup"><span data-stu-id="c2e20-154">The bounds of the Adorner window.</span></span>|  
|`AdornerWindowRegion`|<span data-ttu-id="c2e20-155">A região da janela Adorno.</span><span class="sxs-lookup"><span data-stu-id="c2e20-155">The region of the Adorner window.</span></span>|  
|`AdornerWindowGraphics`|<span data-ttu-id="c2e20-156">Um contexto gráfico da janela Adorno.</span><span class="sxs-lookup"><span data-stu-id="c2e20-156">A graphics context for the Adorner window.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="c2e20-157">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="c2e20-157">Public Methods</span></span>  
  
|||  
|-|-|  
|`ComponentRectInDesignerFrame`|<span data-ttu-id="c2e20-158">Retorna os limites do componente convertidos em coordenadas de quadro de designer.</span><span class="sxs-lookup"><span data-stu-id="c2e20-158">Returns the bounds of the component translated into designer frame coordinates.</span></span>|  
|`InvalidateAdorner`|<span data-ttu-id="c2e20-159">Invalida a janela Adorno.</span><span class="sxs-lookup"><span data-stu-id="c2e20-159">Invalidates the Adorner window.</span></span>|  
|`PointToAdorner`|<span data-ttu-id="c2e20-160">Retorna um ponto em coordenadas de tela convertidas em coordenadas da janela Adorno.</span><span class="sxs-lookup"><span data-stu-id="c2e20-160">Returns a point in screen coordinates translated to Adorner window coordinates.</span></span>|  
  
### <a name="microsoftreportdesignerexpressioneditor"></a><span data-ttu-id="c2e20-161">Microsoft.ReportDesigner.ExpressionEditor</span><span class="sxs-lookup"><span data-stu-id="c2e20-161">Microsoft.ReportDesigner.ExpressionEditor</span></span>  
 <span data-ttu-id="c2e20-162">Esta classe pode ser usada de seu controle de item de relatório personalizado em tempo de design para invocar o Editor de Expressão.</span><span class="sxs-lookup"><span data-stu-id="c2e20-162">This class can be used from your custom report item design-time control to invoke the Expression Editor.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="c2e20-163">Métodos públicos</span><span class="sxs-lookup"><span data-stu-id="c2e20-163">Public Methods</span></span>  
  
|||  
|-|-|  
|`EditValue`|<span data-ttu-id="c2e20-164">Invoca o Editor de Expressão, inicializado com o valor de objeto determinado.</span><span class="sxs-lookup"><span data-stu-id="c2e20-164">Invokes the Expression Editor, initialized with the given object value.</span></span>|  
  
### <a name="microsoftreportdesignerifieldsdataobject"></a><span data-ttu-id="c2e20-165">Microsoft.ReportDesigner.IFieldsDataObject</span><span class="sxs-lookup"><span data-stu-id="c2e20-165">Microsoft.ReportDesigner.IFieldsDataObject</span></span>  
 <span data-ttu-id="c2e20-166">Esta classe é uma coleção de campos do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], usada para dar suporte a eventos de arrastar e soltar no ambiente de design.</span><span class="sxs-lookup"><span data-stu-id="c2e20-166">This class is a collection of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] fields, and is used to support drag-and-drop events in the design environment.</span></span> <span data-ttu-id="c2e20-167">Herdada de `IReportItemDataObject`.</span><span class="sxs-lookup"><span data-stu-id="c2e20-167">Inherits from `IReportItemDataObject`.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="c2e20-168">Propriedades públicas</span><span class="sxs-lookup"><span data-stu-id="c2e20-168">Public Properties</span></span>  
  
|||  
|-|-|  
|`DataSetName`|<span data-ttu-id="c2e20-169">O nome do conjunto de dados que contém os campos a serem soltos.</span><span class="sxs-lookup"><span data-stu-id="c2e20-169">The name of the dataset containing the fields to be dropped.</span></span>|  
|`Fields`|<span data-ttu-id="c2e20-170">A coleção de campos (`Microsoft.ReportDesigner.Field`) a serem soltos.</span><span class="sxs-lookup"><span data-stu-id="c2e20-170">The collection of fields (`Microsoft.ReportDesigner.Field`) to be dropped.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2e20-171">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2e20-171">See Also</span></span>  
 <span data-ttu-id="c2e20-172">[Linguagem de definição de relatório &#40;SSRS&#41;](../reports/report-definition-language-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c2e20-172">[Report Definition Language &#40;SSRS&#41;](../reports/report-definition-language-ssrs.md) </span></span>  
 <span data-ttu-id="c2e20-173">[Criando um componente de tempo de execução de item de relatório personalizado](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="c2e20-173">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 [<span data-ttu-id="c2e20-174">Criando um componente de tempo de design de item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="c2e20-174">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
  
  
