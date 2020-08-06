---
title: Implementando metadados externos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- disconnected validation [Integration Services]
- connected validation [Integration Services]
- custom data flow components [Integration Services], validating
- validation [Integration Services], components
- metadata [Integration Services]
- data flow components [Integration Services], validating
- data flow components [Integration Services], external metadata
- custom data flow components [Integration Services], external metadata
- external metadata [Integration Services]
ms.assetid: 8f5bd3ed-3e79-43a4-b6c1-435e4c2cc8cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a6b77229c528bc08057e662a4b3761d1daf732f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679447"
---
# <a name="implementing-external-metadata"></a><span data-ttu-id="566cb-102">Implementando metadados externos</span><span class="sxs-lookup"><span data-stu-id="566cb-102">Implementing External Metadata</span></span>
  <span data-ttu-id="566cb-103">Quando um componente é desconectado de sua fonte de dados, você pode validar as colunas nas coleções de colunas de entrada e saída com base nas colunas da fonte de dados externa por meio da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100>.</span><span class="sxs-lookup"><span data-stu-id="566cb-103">When a component is disconnected from its data source, you can validate the columns in the input and output column collections against the columns at its external data source by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100> interface.</span></span> <span data-ttu-id="566cb-104">Essa interface permite que você mantenha um instantâneo das colunas na fonte de dados externa e as mapeie para as colunas da coleção de colunas de entrada e saída do componente.</span><span class="sxs-lookup"><span data-stu-id="566cb-104">This interface lets you maintain a snapshot of the columns at the external data source and map these columns to the columns in the input and output column collection of the component.</span></span>  
  
 <span data-ttu-id="566cb-105">A implementação de colunas de metadados externos adiciona uma camada de sobrecarga e complexidade ao desenvolvimento do componente, já que você deve fazer a manutenção e a validação em uma coleção de colunas adicionais. Entretanto, a capacidade de evitar viagens dispendiosas de ida e volta ao servidor para validação pode tornar esse trabalho de desenvolvimento compensador.</span><span class="sxs-lookup"><span data-stu-id="566cb-105">Implementing external metadata columns adds a layer of overhead and complexity to component development, because you must maintain and validate against an additional column collection, but the ability to avoid expensive round trips to the server for validation may make this development work worthwhile.</span></span>  
  
## <a name="populating-external-metadata-columns"></a><span data-ttu-id="566cb-106">Preenchendo colunas de metadados externos</span><span class="sxs-lookup"><span data-stu-id="566cb-106">Populating External Metadata Columns</span></span>  
 <span data-ttu-id="566cb-107">Normalmente, colunas de metadados externas são adicionadas à coleção quando a coluna de entrada ou de saída correspondente é criada.</span><span class="sxs-lookup"><span data-stu-id="566cb-107">External metadata columns are typically added to the collection when the corresponding input or output column is created.</span></span> <span data-ttu-id="566cb-108">Novas colunas são criadas chamando-se o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A>.</span><span class="sxs-lookup"><span data-stu-id="566cb-108">New columns are created by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A> method.</span></span> <span data-ttu-id="566cb-109">As propriedades da coluna são definidas para corresponder à fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="566cb-109">The properties of the column are then set to match the external data source.</span></span>  
  
 <span data-ttu-id="566cb-110">A coluna de metadados externos é mapeada para a coluna de entrada e saída correspondente atribuindo-se a ID da coluna de metadados externos à propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> da coluna de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="566cb-110">The external metadata column is mapped to the corresponding input or output column by assigning the ID of the external metadata column to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property of the input or output column.</span></span> <span data-ttu-id="566cb-111">Isto permite que você localize com facilidade a coluna de metadados externos para uma coluna de entrada ou saída específica usando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A> da coleção.</span><span class="sxs-lookup"><span data-stu-id="566cb-111">This lets you locate the external metadata column easily for a specific input or output column by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A> method of the collection.</span></span>  
  
 <span data-ttu-id="566cb-112">O exemplo a seguir mostra como criar uma coluna de metadados externos e mapear a coluna para uma coluna de saída ao definir a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A>.</span><span class="sxs-lookup"><span data-stu-id="566cb-112">The following example shows how to create an external metadata column and then map the column to an output column by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property.</span></span>  
  
```csharp  
public void CreateExternalMetaDataColumn(IDTSOutput100 output, int outputColumnID )  
{  
    IDTSOutputColumn100 oColumn = output.OutputColumnCollection.GetObjectByID(outputColumnID);  
    IDTSExternalMetadataColumn100 eColumn = output.ExternalMetadataColumnCollection.New();  
  
    eColumn.DataType = oColumn.DataType;  
    eColumn.Precision = oColumn.Precision;  
    eColumn.Scale = oColumn.Scale;  
    eColumn.Length = oColumn.Length;  
    eColumn.CodePage = oColumn.CodePage;  
  
    oColumn.ExternalMetadataColumnID = eColumn.ID;  
}  
```  
  
```vb  
Public Sub CreateExternalMetaDataColumn(ByVal output As IDTSOutput100, ByVal outputColumnID As Integer)   
 Dim oColumn As IDTSOutputColumn100 = output.OutputColumnCollection.GetObjectByID(outputColumnID)   
 Dim eColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New   
 eColumn.DataType = oColumn.DataType   
 eColumn.Precision = oColumn.Precision   
 eColumn.Scale = oColumn.Scale   
 eColumn.Length = oColumn.Length   
 eColumn.CodePage = oColumn.CodePage   
 oColumn.ExternalMetadataColumnID = eColumn.ID   
End Sub  
```  
  
## <a name="validating-with-external-metadata-columns"></a><span data-ttu-id="566cb-113">Validando com colunas de metadados externos</span><span class="sxs-lookup"><span data-stu-id="566cb-113">Validating with External Metadata Columns</span></span>  
 <span data-ttu-id="566cb-114">A validação requer etapas adicionais para componentes que mantêm uma coleção de colunas de metadados externos, porque você deve validar com base em uma coleção adicional de colunas.</span><span class="sxs-lookup"><span data-stu-id="566cb-114">Validation requires additional steps for components that maintain an external metadata column collection, because you must validate against an additional collection of columns.</span></span> <span data-ttu-id="566cb-115">A validação pode ser dividida em validação conectada ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="566cb-115">Validation can be divided into connected validation or disconnected validation.</span></span>  
  
### <a name="connected-validation"></a><span data-ttu-id="566cb-116">Validação conectada</span><span class="sxs-lookup"><span data-stu-id="566cb-116">Connected Validation</span></span>  
 <span data-ttu-id="566cb-117">Quando um componente é conectado a uma fonte de dados externa, as colunas nas coleções de entrada ou saída são verificadas diretamente na fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="566cb-117">When a component is connected to an external data source, the columns in the input or output collections are verified directly against the external data source.</span></span> <span data-ttu-id="566cb-118">Adicionalmente, as colunas na coleção de metadados externos devem ser validadas.</span><span class="sxs-lookup"><span data-stu-id="566cb-118">Additionally, the columns in the external metadata collection must be validated.</span></span> <span data-ttu-id="566cb-119">Isso é necessário porque a coleção de metadados externos pode ser modificada por meio do **Editor Avançado** no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] e as alterações feitas à coleção não são detectáveis.</span><span class="sxs-lookup"><span data-stu-id="566cb-119">This is required because the external metadata collection can be modified by using the **Advanced Editor** in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and changes made to the collection are not detectable.</span></span> <span data-ttu-id="566cb-120">Portanto, quando conectados, os componentes devem verificar se as colunas da coleção de colunas de metadados externos continuam refletindo as colunas da fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="566cb-120">Therefore, when connected, components must make sure that the columns in the external metadata column collection continue to reflect the columns at the external data source.</span></span>  
  
 <span data-ttu-id="566cb-121">Você pode optar por ocultar a coleção de metadados externos no **Editor avançado** definindo a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> propriedade da coleção como `false` .</span><span class="sxs-lookup"><span data-stu-id="566cb-121">You may choose to hide the external metadata collection in the **Advanced Editor** by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> property of the collection to `false`.</span></span> <span data-ttu-id="566cb-122">Entretanto, esse procedimento também oculta a guia **Mapeamento de Coluna** do editor, a qual permite que os usuários mapeiem as colunas da coleção de entrada ou saída para as colunas da coleção de colunas de metadados externos.</span><span class="sxs-lookup"><span data-stu-id="566cb-122">However this also hides the **Column Mapping** tab of the editor, which lets users map columns from the input or output collection to the columns in the external metadata column collection.</span></span> <span data-ttu-id="566cb-123">A definição desta propriedade como `false` não impede que os desenvolvedores modifiquem programaticamente a coleção, mas, efetivamente, fornece um nível de proteção para a coleção de colunas de metadados externos de um componente que é utilizado exclusivamente no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="566cb-123">Setting this property to `false` does not prevent developers from programmatically modifying the collection, but it does provide a level of protection for the external metadata column collection of a component that is used exclusively in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="disconnected-validation"></a><span data-ttu-id="566cb-124">Validação desconectada</span><span class="sxs-lookup"><span data-stu-id="566cb-124">Disconnected Validation</span></span>  
 <span data-ttu-id="566cb-125">Quando um componente é desconectado de uma fonte de dados externa, a validação é simplificada porque as colunas da coleção de entrada ou saída são verificadas diretamente com base nas colunas da coleção de metadados externos e não com base na fonte externa.</span><span class="sxs-lookup"><span data-stu-id="566cb-125">When a component is disconnected from an external data source, validation is simplified because the columns in the input or output collection are verified directly against the columns in the external metadata collection and not against the external source.</span></span> <span data-ttu-id="566cb-126">Um componente deve executar a validação desconectada quando a conexão com sua fonte de dados externa não tiver sido estabelecida ou quando a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> for `false`.</span><span class="sxs-lookup"><span data-stu-id="566cb-126">A component should perform disconnected validation when the connection to its external data source has not been established, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="566cb-127">O exemplo de código a seguir demonstra uma implementação de um componente que executa validação com base em sua coleção de colunas de metadados externos.</span><span class="sxs-lookup"><span data-stu-id="566cb-127">The following code example demonstrates an implementation of a component that performs validation against its external metadata column collection.</span></span>  
  
```csharp  
public override DTSValidationStatus Validate()  
{  
    if( this.isConnected && ComponentMetaData.ValidateExternalMetaData )  
    {  
        // TODO: Perform connected validation.  
    }  
    else  
    {  
        // TODO: Perform disconnected validation.  
    }  
}  
```  
  
```vb  
Public  Overrides Function Validate() As DTSValidationStatus   
 If Me.isConnected AndAlso ComponentMetaData.ValidateExternalMetaData Then   
  ' TODO: Perform connected validation.  
 Else   
  ' TODO: Perform disconnected validation.  
 End If   
End Function  
```  
  
<span data-ttu-id="566cb-128">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="566cb-128">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="566cb-129">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="566cb-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="566cb-130">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="566cb-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="566cb-131">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="566cb-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="566cb-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="566cb-132">See Also</span></span>  
 [<span data-ttu-id="566cb-133">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="566cb-133">Data Flow</span></span>](../../data-flow/data-flow.md)  
  
  
