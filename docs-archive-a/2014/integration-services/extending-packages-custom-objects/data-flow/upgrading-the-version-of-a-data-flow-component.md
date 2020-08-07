---
title: Atualizar a versão de um componente de fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- PerformUpgrade method
- custom data flow components [Integration Services], upgrading version
- data flow components [Integration Services], upgrading version
- upgrading data flow components [Integration Services]
ms.assetid: c2a298c6-01b3-4ad1-884d-6108165eb56e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f494793a20f1cdcd108553278b82a44daeea75ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583730"
---
# <a name="upgrading-the-version-of-a-data-flow-component"></a><span data-ttu-id="fd217-102">Atualizando a versão de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="fd217-102">Upgrading the Version of a Data Flow Component</span></span>
  <span data-ttu-id="fd217-103">Pacotes criados com uma versão mais antiga do seu componente podem conter metadados que não são mais válidos, como propriedades personalizadas cujo uso foi modificado em versões mais recentes do componente.</span><span class="sxs-lookup"><span data-stu-id="fd217-103">Packages that were created with an older version of your component may contain metadata that is no longer valid, such as custom properties whose usage has been modified in newer versions of the component.</span></span> <span data-ttu-id="fd217-104">É possível substituir o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> da classe base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> para atualizar os metadados salvos anteriormente em pacotes mais antigos, a fim de refletir as propriedades atuais do seu componente.</span><span class="sxs-lookup"><span data-stu-id="fd217-104">You can override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class to update the metadata previously saved in older packages to reflect the current properties of your component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd217-105">Quando você compila novamente um componente personalizado para uma nova versão do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], não é necessário mudar o valor da propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> se as propriedades do componente não tiverem mudado.</span><span class="sxs-lookup"><span data-stu-id="fd217-105">When you recompile a custom component for a new version of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], you do not have to change the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property if the component's properties have not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd217-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="fd217-106">Example</span></span>  
 <span data-ttu-id="fd217-107">O exemplo seguinte contém o código da versão 2.0 de um componente de fluxo de dados fictício.</span><span class="sxs-lookup"><span data-stu-id="fd217-107">The following sample contains code from version 2.0 of a fictitious data flow component.</span></span> <span data-ttu-id="fd217-108">O número da nova versão é definido na propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> do <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fd217-108">The new version number is defined in the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="fd217-109">O componente tem uma propriedade que define como os valores numéricos que excedem um limite são tratados.</span><span class="sxs-lookup"><span data-stu-id="fd217-109">The component has a property that defines how numeric values that exceed a threshold are to be handled.</span></span> <span data-ttu-id="fd217-110">Na versão 1.0 do componente fictício, essa propriedade era denominada `RaiseErrorOnInvalidValue` e aceitou um valor Booleano de verdadeiro ou falso.</span><span class="sxs-lookup"><span data-stu-id="fd217-110">In version 1.0 of the fictitious component, this property was named `RaiseErrorOnInvalidValue` and accepted a Boolean value of true or false.</span></span> <span data-ttu-id="fd217-111">Na versão 2.0 do componente fictício, a propriedade foi renomeada para `InvalidValueHandling` e aceita um entre quatro valores possíveis de uma enumeração personalizada.</span><span class="sxs-lookup"><span data-stu-id="fd217-111">In version 2.0 of the fictitious component, the property has been renamed to `InvalidValueHandling` and accepts one of four possible values from a custom enumeration.</span></span>  
  
 <span data-ttu-id="fd217-112">O método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> substituído no exemplo a seguir realiza as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="fd217-112">The overridden <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the following sample performs the following actions:</span></span>  
  
-   <span data-ttu-id="fd217-113">Obtém a versão atual do componente.</span><span class="sxs-lookup"><span data-stu-id="fd217-113">Gets the current version of the component.</span></span>  
  
-   <span data-ttu-id="fd217-114">Obtém o valor da propriedade personalizada antiga.</span><span class="sxs-lookup"><span data-stu-id="fd217-114">Gets the value of the old custom property.</span></span>  
  
-   <span data-ttu-id="fd217-115">Remove a propriedade antiga da coleção de propriedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="fd217-115">Removes the old property from the custom property collection.</span></span>  
  
-   <span data-ttu-id="fd217-116">Define o valor da nova propriedade personalizada com base no valor da propriedade antiga, se possível.</span><span class="sxs-lookup"><span data-stu-id="fd217-116">Sets the value of the new custom property based on the value of the old property, if possible.</span></span>  
  
-   <span data-ttu-id="fd217-117">Define os metadados da versão para a versão atual do componente.</span><span class="sxs-lookup"><span data-stu-id="fd217-117">Sets the version metadata to the current version of the component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd217-118">O mecanismo de fluxo de dados passa seu próprio número de versão para o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> no parâmetro *pipelineVersion*.</span><span class="sxs-lookup"><span data-stu-id="fd217-118">The data flow engine passes its own version number into the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the *pipelineVersion* parameter.</span></span> <span data-ttu-id="fd217-119">Esse parâmetro não é útil na versão 1.0 do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], mas pode se tornar útil em versões subsequentes.</span><span class="sxs-lookup"><span data-stu-id="fd217-119">This parameter is not useful in version 1.0 of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], but may become useful in subsequent versions.</span></span>  
  
 <span data-ttu-id="fd217-120">O código de exemplo usa somente os dois valores de enumeração, que mapeiam diretamente para os valores Booleanos anteriores para a propriedade personalizada.</span><span class="sxs-lookup"><span data-stu-id="fd217-120">The sample code uses only the two enumeration values that map directly to the prior Boolean values for the custom property.</span></span> <span data-ttu-id="fd217-121">Os usuários podem selecionar os outros valores de enumeração disponíveis pela interface do usuário personalizada do componente, no Editor Avançado, ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="fd217-121">Users can select the other available enumeration values through the component's custom user interface, in the Advanced Editor, or programmatically.</span></span> <span data-ttu-id="fd217-122">Para obter informações sobre como exibir valores de enumeração para uma propriedade personalizada no Editor Avançado, consulte "Criando propriedades personalizadas" em [Métodos de tempo de design de um componente de fluxo de dados](design-time-methods-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="fd217-122">For information on displaying enumeration values for a custom property in the Advanced Editor, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(ComponentType:=ComponentType.Transform, CurrentVersion:=2)> _  
Public Class PerformUpgrade  
  Inherits PipelineComponent  
  
  ' Define the set of possible values for the new custom property.  
  Private Enum InvalidValueHandling  
    Ignore  
    FireInformation  
    FireWarning  
    FireError  
  End Enum  
  
  Public Overloads Overrides Sub PerformUpgrade(ByVal pipelineVersion As Integer)  
  
    ' Obtain the current component version from the attribute.  
    Dim componentAttribute As DtsPipelineComponentAttribute = _  
      CType(Attribute.GetCustomAttribute(Me.GetType, _  
      GetType(DtsPipelineComponentAttribute), False), _  
      DtsPipelineComponentAttribute)  
    Dim currentVersion As Integer = componentAttribute.CurrentVersion  
  
    ' If the component version saved in the package is less than  
    '  the current version, Version 2, perform the upgrade.  
    If ComponentMetaData.Version < currentVersion Then  
  
      ' Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
      ' and then remove the property from the custom property collection.  
      Dim oldValue As Boolean = False  
      Try  
        Dim oldProperty As IDTSCustomProperty100 = _  
          ComponentMetaData.CustomPropertyCollection("RaiseErrorOnInvalidValue")  
        oldValue = CType(oldProperty.Value, Boolean)  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue")  
      Catch ex As Exception  
        ' If the old custom property is not available, ignore the error.  
      End Try  
  
      ' Set the value of the new custom property, InvalidValueHandling,  
      '  by using the appropriate enumeration value.  
      Dim newProperty As IDTSCustomProperty100 = _  
        ComponentMetaData.CustomPropertyCollection("InvalidValueHandling")  
      If oldValue = True Then  
        newProperty.Value = InvalidValueHandling.FireError  
      Else  
        newProperty.Value = InvalidValueHandling.Ignore  
      End If  
  
    End If  
  
    ' Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
[DtsPipelineComponent(ComponentType = ComponentType.Transform, CurrentVersion = 2)]  
public class PerformUpgradeCS :  
  PipelineComponent  
  
  // Define the set of possible values for the new custom property.  
{  
  private enum InvalidValueHandling  
  {  
    Ignore,  
    FireInformation,  
    FireWarning,  
    FireError  
  };  
  
  public override void PerformUpgrade(int pipelineVersion)  
  {  
  
    // Obtain the current component version from the attribute.  
    DtsPipelineComponentAttribute componentAttribute =   
      (DtsPipelineComponentAttribute)Attribute.GetCustomAttribute(this.GetType(), typeof(DtsPipelineComponentAttribute), false);  
    int currentVersion = componentAttribute.CurrentVersion;  
  
    // If the component version saved in the package is less than  
    //  the current version, Version 2, perform the upgrade.  
    if (ComponentMetaData.Version < currentVersion)  
  
    // Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
    // and then remove the property from the custom property collection.  
    {  
      bool oldValue = false;  
      try  
      {  
        IDTSCustomProperty100 oldProperty =   
          ComponentMetaData.CustomPropertyCollection["RaiseErrorOnInvalidValue"];  
        oldValue = (bool)oldProperty.Value;  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue");  
      }  
      catch (Exception ex)  
      {  
        // If the old custom property is not available, ignore the error.  
      }  
  
      // Set the value of the new custom property, InvalidValueHandling,  
      //  by using the appropriate enumeration value.  
      IDTSCustomProperty100 newProperty =   
         ComponentMetaData.CustomPropertyCollection["InvalidValueHandling"];  
      if (oldValue == true)  
      {  
        newProperty.Value = InvalidValueHandling.FireError;  
      }  
      else  
      {  
        newProperty.Value = InvalidValueHandling.Ignore;  
      }  
  
    }  
  
    // Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion;  
  
  }  
  
}  
```  
  
<span data-ttu-id="fd217-123">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="fd217-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="fd217-124">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="fd217-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="fd217-125">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="fd217-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="fd217-126">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="fd217-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
