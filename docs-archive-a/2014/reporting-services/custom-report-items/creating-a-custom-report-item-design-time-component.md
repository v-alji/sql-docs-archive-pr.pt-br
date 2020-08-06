---
title: Criando um componente de item de relatório personalizado em tempo de design | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, creating
ms.assetid: 323fd58a-a462-4c48-b188-77ebc0b4212e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b663dc3b0a9c54d1674bf153ee09dd36e0de7a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569210"
---
# <a name="creating-a-custom-report-item-design-time-component"></a><span data-ttu-id="153b4-102">Criando um componente de tempo de design de item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="153b4-102">Creating a Custom Report Item Design-Time Component</span></span>
  <span data-ttu-id="153b4-103">Um componente em tempo de design de item de relatório personalizado é um controle que pode ser usado no ambiente do Designer de Relatórios do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="153b4-103">A custom report item design-time component is a control that can be used in the Visual Studio Report Designer environment.</span></span> <span data-ttu-id="153b4-104">O componente em tempo de design de item de relatório personalizado oferece uma superfície de design ativada que pode aceitar operações de arrastar e soltar, a integração ao pesquisador de propriedade [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] e a capacidade de oferecer editores de propriedade personalizados.</span><span class="sxs-lookup"><span data-stu-id="153b4-104">The custom report item design-time component provides an activated design surface that can accept drag-and-drop operations, integration with the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser, and the ability to provide custom property editors.</span></span>  
  
 <span data-ttu-id="153b4-105">Com um componente em tempo de design de item de relatório personalizado, o usuário pode posicionar um item de relatório personalizado em um relatório no ambiente de design, definir propriedades de dados personalizadas no item de relatório personalizado e, depois, salvar esse item como parte do projeto de relatório.</span><span class="sxs-lookup"><span data-stu-id="153b4-105">With a custom report item design-time component, the user can position a custom report item on a report in the design environment, set custom data properties on the custom report item, and then save the custom report item as part of the report project.</span></span>  
  
 <span data-ttu-id="153b4-106">As propriedades definidas usando o componente em tempo de design no ambiente de desenvolvimento são serializadas e desserializadas pelo ambiente de design de host e, depois, armazenadas como elementos no arquivo em linguagem RDL.</span><span class="sxs-lookup"><span data-stu-id="153b4-106">The properties that are set using the design-time component in the development environment are serialized and deserialized by the host design environment and then stored as elements in the Report Definition Language (RDL) file.</span></span> <span data-ttu-id="153b4-107">Quando o relatório é executado pelo processador de relatório, as propriedades definidas usando o componente em tempo de design são passadas pelo processador de relatório para um componente em tempo de execução de item de relatório personalizado, que renderiza o item de relatório personalizado e o devolve ao processador de relatório.</span><span class="sxs-lookup"><span data-stu-id="153b4-107">When the report is executed by the report processor, the properties that are set using the design-time component are passed by the report processor to a custom report item run-time component, which renders the custom report item and passes it back to the report processor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="153b4-108">O componente de item de relatório personalizado em tempo de design implementado como um componente do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="153b4-108">The custom report item design-time component is implemented as a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] component.</span></span> <span data-ttu-id="153b4-109">Este documento descreverá detalhes de implementação específicos do componente em tempo de design de item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="153b4-109">This document will describe implementation details specific to the custom report item design-time component.</span></span> <span data-ttu-id="153b4-110">Para obter mais informações sobre como desenvolver componentes usando o [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], consulte [Componentes do Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="153b4-110">For more information about developing components using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see [Components in Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576) in the MSDN library.</span></span>  
  
 <span data-ttu-id="153b4-111">Para obter uma amostra de um item de relatório personalizado totalmente implementado, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="153b4-111">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="implementing-a-design-time-component"></a><span data-ttu-id="153b4-112">Implementando um componente em tempo de design</span><span class="sxs-lookup"><span data-stu-id="153b4-112">Implementing a Design-Time Component</span></span>  
 <span data-ttu-id="153b4-113">A classe principal de um componente em tempo de design de item de relatório personalizado que é herdada da classe `Microsoft.ReportDesigner.CustomReportItemDesigner`.</span><span class="sxs-lookup"><span data-stu-id="153b4-113">The main class of a custom report item design-time component is inherited from the `Microsoft.ReportDesigner.CustomReportItemDesigner` class.</span></span> <span data-ttu-id="153b4-114">Além dos atributos padrão usados para um controle [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], sua classe de componente deve definir um atributo `CustomReportItem`.</span><span class="sxs-lookup"><span data-stu-id="153b4-114">In addition to the standard attributes used for a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] control, your component class should define a `CustomReportItem` attribute.</span></span> <span data-ttu-id="153b4-115">Esse atributo deve corresponder ao nome do item de relatório personalizado conforme definido no arquivo reportserver.config.</span><span class="sxs-lookup"><span data-stu-id="153b4-115">This attribute must correspond to the name of the custom report item as it is defined in the reportserver.config file.</span></span> <span data-ttu-id="153b4-116">Para obter uma lista de atributos do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], consulte Atributos na documentação do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="153b4-116">For a list of [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] attributes, see Attributes in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
 <span data-ttu-id="153b4-117">O seguinte exemplo de código mostra atributos que estão sendo aplicados a um controle em tempo de design de item de relatório personalizado:</span><span class="sxs-lookup"><span data-stu-id="153b4-117">The following code example shows attributes being applied to a custom report item design-time control:</span></span>  
  
```csharp  
namespace PolygonsCRI  
{  
    [LocalizedName("Polygons")]  
    [Editor(typeof(CustomEditor), typeof(ComponentEditor))]  
        [ToolboxBitmap(typeof(PolygonsDesigner),"Polygons.ico")]  
        [CustomReportItem("Polygons")]  
  
    public class PolygonsDesigner : CustomReportItemDesigner  
    {  
...  
```  
  
### <a name="initializing-the-component"></a><span data-ttu-id="153b4-118">Inicializando o componente</span><span class="sxs-lookup"><span data-stu-id="153b4-118">Initializing the Component</span></span>  
 <span data-ttu-id="153b4-119">Você passa propriedades especificadas pelo usuário para um item de relatório personalizado usando uma classe <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData>.</span><span class="sxs-lookup"><span data-stu-id="153b4-119">You pass user-specified properties for a custom report item using a <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class.</span></span> <span data-ttu-id="153b4-120">Sua implementação da classe `CustomReportItemDesigner` deve substituir o método `InitializeNewComponent` para criar uma nova instância da classe <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> do seu componente e defini-la com valores padrão.</span><span class="sxs-lookup"><span data-stu-id="153b4-120">Your implementation of the `CustomReportItemDesigner` class should override the `InitializeNewComponent` method to create a new instance of your component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class and set it to default values.</span></span>  
  
 <span data-ttu-id="153b4-121">O seguinte exemplo de código mostra um exemplo de uma classe de componente em tempo de design de item de relatório personalizado que substitui o método `CustomReportItemDesigner.InitializeNewComponent` para inicializar a classe <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> do componente:</span><span class="sxs-lookup"><span data-stu-id="153b4-121">The following code example shows an example of a custom report item design-time component class overriding the `CustomReportItemDesigner.InitializeNewComponent` method to initialize the component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class:</span></span>  
  
```csharp  
public override void InitializeNewComponent()  
        {  
            CustomData = new CustomData();  
            CustomData.DataRowHierarchy = new DataHierarchy();  
  
            // Shape grouping  
            CustomData.DataRowHierarchy.DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].Group.Name = Name + "_Shape";  
            CustomData.DataRowHierarchy.DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Point grouping  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.Name = Name + "_Point";  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Static column  
            CustomData.DataColumnHierarchy = new DataHierarchy();  
            CustomData.DataColumnHierarchy.DataMembers.Add(new DataMember());  
  
            // Points  
            IList<IList<DataValue>> dataValues = new List<IList<DataValue>>();  
            CustomData.DataRows.Add(dataValues);  
            CustomData.DataRows[0].Add(new List<DataValue>());  
            CustomData.DataRows[0][0].Add(NewDataValue("X", ""));  
            CustomData.DataRows[0][0].Add(NewDataValue("Y", ""));  
        }  
```  
  
### <a name="modifying-component-properties"></a><span data-ttu-id="153b4-122">Modificando propriedades do componente</span><span class="sxs-lookup"><span data-stu-id="153b4-122">Modifying Component Properties</span></span>  
 <span data-ttu-id="153b4-123">Você pode modificar propriedades `CustomData` no ambiente de design de diversas maneiras.</span><span class="sxs-lookup"><span data-stu-id="153b4-123">You can modify `CustomData` properties in the design environment in several ways.</span></span> <span data-ttu-id="153b4-124">Você pode modificar quaisquer propriedades expostas pelo componente em tempo de design que estejam marcadas com o atributo <xref:System.ComponentModel.BrowsableAttribute> usando o pesquisador de propriedade do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="153b4-124">You can modify any properties that are exposed by the design-time component that are marked with the <xref:System.ComponentModel.BrowsableAttribute> attribute by using the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser.</span></span> <span data-ttu-id="153b4-125">Além disso, você pode modificar as propriedades arrastando itens para a superfície de design do item de relatório personalizado ou clicando com o botão direito do mouse no controle do ambiente de design e selecionando **Propriedades** no menu de atalho para exibir uma janela de propriedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="153b4-125">In addition, you can modify properties by dragging items onto the custom report item's design surface, or by right-clicking the control in the design environment and selecting **Properties** on the shortcut menu to display a custom properties window.</span></span>  
  
 <span data-ttu-id="153b4-126">O seguinte exemplo de código mostra uma propriedade `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData` que tem o atributo <xref:System.ComponentModel.BrowsableAttribute> aplicado:</span><span class="sxs-lookup"><span data-stu-id="153b4-126">The following code example shows a `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData` property that has the <xref:System.ComponentModel.BrowsableAttribute> attribute applied:</span></span>  
  
```csharp  
[Browsable(true), Category("Data")]  
public string DataSetName  
{  
      get  
      {  
         return CustomData.DataSetName;  
      }  
      set  
      {  
         CustomData.DataSetName = value;  
      }  
   }  
  
```  
  
 <span data-ttu-id="153b4-127">Você pode fornecer ao componente em tempo de design uma caixa de diálogo de editor de propriedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="153b4-127">You can provide your design-time component with a custom properties editor dialog box.</span></span> <span data-ttu-id="153b4-128">A implementação do editor de propriedades personalizadas deve ser herdada da classe <xref:System.ComponentModel.ComponentEditor> e deve criar uma instância de uma caixa de diálogo a ser usada na edição de propriedades.</span><span class="sxs-lookup"><span data-stu-id="153b4-128">The custom property editor implementation should inherit from the <xref:System.ComponentModel.ComponentEditor> class, and it should create an instance of a dialog box that can be used for property editing.</span></span>  
  
 <span data-ttu-id="153b4-129">O seguinte exemplo mostra uma implementação de uma classe herdada de <xref:System.ComponentModel.ComponentEditor> e exibe uma caixa de diálogo de editor de propriedade personalizadas:</span><span class="sxs-lookup"><span data-stu-id="153b4-129">The following example shows an implementation of a class that inherits from <xref:System.ComponentModel.ComponentEditor> and displays a custom property editor dialog box:</span></span>  
  
```csharp  
internal sealed class CustomEditor : ComponentEditor  
{  
   public override bool EditComponent(  
      ITypeDescriptorContext context, object component)  
    {  
     PolygonsDesigner designer = (PolygonsDesigner)component;  
     PolygonProperties dialog = new PolygonProperties();  
     dialog.m_designerComponent = designer;  
     DialogResult result = dialog.ShowDialog();  
     if (result == DialogResult.OK)  
     {  
        designer.Invalidate();  
        designer.ChangeService().OnComponentChanged(designer, null, null, null);  
        return true;  
     }  
     else  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="153b4-130">Sua caixa de diálogo de editor de propriedades personalizadas pode invocar o Editor de Expressão do Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="153b4-130">Your custom property editor dialog box can invoke the Report Designer Expression Editor.</span></span> <span data-ttu-id="153b4-131">Neste exemplo, o Editor de Expressão é invocado quando o usuário seleciona o primeiro elemento na caixa de combinação:</span><span class="sxs-lookup"><span data-stu-id="153b4-131">In the following example, the Expression Editor is invoked when the user selects the first element in the combo box:</span></span>  
  
```csharp  
private void EditableCombo_SelectedIndexChanged(object sender,   
    EventArgs e)  
{  
   ComboBox combo = (ComboBox)sender;  
   if (combo.SelectedIndex == 0 && m_launchEditor)  
   {  
      m_launchEditor = false;  
      ExpressionEditor editor = new ExpressionEditor();  
      string newValue;  
      newValue = (string)editor.EditValue(null, m_designerComponent.Site, m_oldComboValue);  
      combo.Items[0] = newValue;  
   }  
}  
  
```  
  
### <a name="using-designer-verbs"></a><span data-ttu-id="153b4-132">Usando verbos do designer</span><span class="sxs-lookup"><span data-stu-id="153b4-132">Using Designer Verbs</span></span>  
 <span data-ttu-id="153b4-133">Um verbo do designer é um comando de menu vinculado a um manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="153b4-133">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="153b4-134">Você pode adicionar verbos do designer que aparecerão no menu de atalho de um componente quando o controle em tempo de execução do seu item de relatório personalizado estiver sendo usado no ambiente de design.</span><span class="sxs-lookup"><span data-stu-id="153b4-134">You can add designer verbs that will appear in a component's shortcut menu when your custom report item run-time control is being used in the design environment.</span></span> <span data-ttu-id="153b4-135">Você pode retornar a lista de verbos do designer disponíveis de seu componente em tempo de execução usando a propriedade `Verbs`.</span><span class="sxs-lookup"><span data-stu-id="153b4-135">You can return the list of available designer verbs from your run-time component by using the `Verbs` property.</span></span>  
  
 <span data-ttu-id="153b4-136">Este exemplo de código mostra um verbo do designer e um manipulador de eventos que está sendo adicionado ao <xref:System.ComponentModel.Design.DesignerVerbCollection>, bem como o código do manipulador de eventos:</span><span class="sxs-lookup"><span data-stu-id="153b4-136">The following code example shows a designer verb and an event handler being added to the <xref:System.ComponentModel.Design.DesignerVerbCollection>, as well as the event handler code:</span></span>  
  
```csharp  
public override DesignerVerbCollection Verbs  
{  
    get  
    {  
        if (m_verbs == null)  
        {  
            m_verbs = new DesignerVerbCollection();  
            m_verbs.Add(new DesignerVerb("Proportional Scaling", new EventHandler(OnProportionalScaling)));  
         m_verbs[0].Checked = (GetCustomProperty("poly:Proportional") == bool.TrueString);  
        }  
  
        return m_verbs;  
    }  
}  
  
private void OnProportionalScaling(object sender, EventArgs e)  
{  
   bool proportional = !  
        (GetCustomProperty("poly:Proportional") == bool.TrueString);  
   m_verbs[0].Checked = proportional;  
   SetCustomProperty("poly:Proportional", proportional.ToString());  
   ChangeService().OnComponentChanged(this, null, null, null);  
   Invalidate();  
}  
```  
  
### <a name="using-adornments"></a><span data-ttu-id="153b4-137">Usando adornos</span><span class="sxs-lookup"><span data-stu-id="153b4-137">Using Adornments</span></span>  
 <span data-ttu-id="153b4-138">Classes de item de relatório personalizadas também podem implementar uma classe `Microsoft.ReportDesigner.Design.Adornment`.</span><span class="sxs-lookup"><span data-stu-id="153b4-138">Custom report item classes can also implement a `Microsoft.ReportDesigner.Design.Adornment` class.</span></span> <span data-ttu-id="153b4-139">Um adorno permite que o controle de item de relatório personalizado forneça áreas fora do retângulo principal da superfície de design.</span><span class="sxs-lookup"><span data-stu-id="153b4-139">An adornment allows the custom report item control to provide areas outside the main rectangle of the design surface.</span></span> <span data-ttu-id="153b4-140">Essas áreas podem tratar eventos de interface do usuário, tais como cliques de mouse e operações de arrastar e soltar.</span><span class="sxs-lookup"><span data-stu-id="153b4-140">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span> <span data-ttu-id="153b4-141">A `Adornment` classe que é definida no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` namespace é uma implementação de passagem da <xref:System.Windows.Forms.Design.Behavior.Adorner> classe encontrada em Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="153b4-141">The `Adornment` class that is defined in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` namespace is a pass-through implementation of the <xref:System.Windows.Forms.Design.Behavior.Adorner> class found in Windows Forms.</span></span> <span data-ttu-id="153b4-142">Para obter a documentação completa sobre a `Adorner` classe, consulte [visão geral do serviço de comportamento](https://go.microsoft.com/fwlink/?LinkId=116673) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="153b4-142">For complete documentation on the `Adorner` class, see [Behavior Service Overview](https://go.microsoft.com/fwlink/?LinkId=116673) in the MSDN library.</span></span> <span data-ttu-id="153b4-143">Para obter um exemplo de código que implementa uma `Microsoft.ReportDesigner.Design.Adornment` classe, consulte [SQL Server Reporting Services exemplos de produto](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="153b4-143">For sample code that implements a `Microsoft.ReportDesigner.Design.Adornment` class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
 <span data-ttu-id="153b4-144">Para obter mais informações sobre como programar e usar o Windows Forms no [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], consulte estes tópicos no biblioteca MSDN:</span><span class="sxs-lookup"><span data-stu-id="153b4-144">For more information about programming and using Windows Forms in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], see these topics in the MSDN Library:</span></span>  
  
-   <span data-ttu-id="153b4-145">Atributos em tempo de design para componentes</span><span class="sxs-lookup"><span data-stu-id="153b4-145">Design-Time Attributes for Components</span></span>  
  
-   <span data-ttu-id="153b4-146">Componentes do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span><span class="sxs-lookup"><span data-stu-id="153b4-146">Components in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span></span>  
  
-   <span data-ttu-id="153b4-147">Passo a passo: Criando um controle do Windows Forms que aproveita recursos em tempo de design do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="153b4-147">Walkthrough: Creating a Windows Forms Control that Takes Advantage of Visual Studio Design-Time Features</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="153b4-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="153b4-148">See Also</span></span>  
 <span data-ttu-id="153b4-149">[Arquitetura de item de relatório personalizado](custom-report-item-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="153b4-149">[Custom Report Item Architecture](custom-report-item-architecture.md) </span></span>  
 <span data-ttu-id="153b4-150">[Criando um componente de tempo de execução de item de relatório personalizado](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="153b4-150">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="153b4-151">[Bibliotecas de classe de item de relatório personalizado](custom-report-item-class-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="153b4-151">[Custom Report Item Class Libraries](custom-report-item-class-libraries.md) </span></span>  
 [<span data-ttu-id="153b4-152">Como: implantar um Item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="153b4-152">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
  
  
