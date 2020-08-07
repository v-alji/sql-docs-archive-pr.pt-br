---
title: Descrição XML do fluxo de trabalho personalizado (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e267e5f4-38bb-466d-82e8-871eabeec07e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77906426ddb901ec422367bf30aabef2e532ad06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584171"
---
# <a name="custom-workflow-xml-description-master-data-services"></a><span data-ttu-id="61e0b-102">Descrição XML do fluxo de trabalho personalizado (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61e0b-102">Custom Workflow XML Description (Master Data Services)</span></span>
  <span data-ttu-id="61e0b-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] , o método [Microsoft. MasterDataServices. WorkflowTypeExtender. IWorkflowTypeExtender. StartWorkflow \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) é chamado por SQL Server serviço de integração de fluxo de trabalho do MDS quando um fluxo de trabalho é iniciado.</span><span class="sxs-lookup"><span data-stu-id="61e0b-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)], the [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) method is called by SQL Server MDS Workflow Integration Service when a workflow starts.</span></span> <span data-ttu-id="61e0b-104">Este método recebe metadados e dados sobre o item que disparou a regra de negócio do fluxo de trabalho como um bloco de XML.</span><span class="sxs-lookup"><span data-stu-id="61e0b-104">This method receives metadata and data about the item that triggered the workflow business rule as a block of XML.</span></span> <span data-ttu-id="61e0b-105">Para obter o código de exemplo que implementa um manipulador de fluxo de trabalho, consulte [Exemplo de fluxo de trabalho personalizado&#40;Master Data Services&#41;](create-a-custom-workflow-example.md).</span><span class="sxs-lookup"><span data-stu-id="61e0b-105">For example code that implements a workflow handler, see [Custom Workflow Example &#40;Master Data Services&#41;](create-a-custom-workflow-example.md).</span></span>  
  
 <span data-ttu-id="61e0b-106">O seguinte exemplo mostra como deve ser a aparência do XML enviado ao manipulador de fluxo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="61e0b-106">The following example shows what the XML that is sent to the workflow handler might look like:</span></span>  
  
```scr  
<ExternalAction>  
  <Type>TEST</Type>  
  <SendData>1</SendData>  
  <Server_URL>This is my test!</Server_URL>  
  <Action_ID>Test Workflow</Action_ID>  
  <Model_ID>5</Model_ID>  
  <Model_Name>Customer</Model_Name>  
  <Entity_ID>34</Entity_ID>  
  <Entity_Name>Customer</Entity_Name>  
  <Version_ID>8</Version_ID>  
  <MemberType_ID>1</MemberType_ID>  
  <Member_ID>12</Member_ID>  
  <MemberData>  
    <ID>12</ID>  
    <Version_ID>8</Version_ID>  
    <ValidationStatus_ID>3</ValidationStatus_ID>  
    <ChangeTrackingMask>0</ChangeTrackingMask>  
    <EnterDTM>2011-02-25T20:16:36.650</EnterDTM>  
    <EnterUserID>2</EnterUserID>  
    <EnterUserName>MyUserName</EnterUserName>  
    <EnterUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</EnterUserMuid>  
    <EnterVersionId>8</EnterVersionId>  
    <EnterVersionName>VERSION_1</EnterVersionName>  
    <EnterVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</EnterVersionMuid>  
    <LastChgDTM>2011-02-25T20:16:36.650</LastChgDTM>  
    <LastChgUserID>2</LastChgUserID>  
    <LastChgUserName>MyUserName</LastChgUserName>  
    <LastChgUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</LastChgUserMuid>  
    <LastChgVersionId>8</LastChgVersionId>  
    <LastChgVersionName>VERSION_1</LastChgVersionName>  
    <LastChgVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</LastChgVersionMuid>  
    <Name>Test Customer</Name>  
    <Code>TC</Code>  
  </MemberData>  
</ExternalAction>  
```  
  
 <span data-ttu-id="61e0b-107">A tabela a seguir descreve algumas das marcas contidas neste XML.</span><span class="sxs-lookup"><span data-stu-id="61e0b-107">The following table describes some of the tags contained in this XML:</span></span>  
  
|<span data-ttu-id="61e0b-108">Marca</span><span class="sxs-lookup"><span data-stu-id="61e0b-108">Tag</span></span>|<span data-ttu-id="61e0b-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="61e0b-109">Description</span></span>|  
|---------|-----------------|  
|\<Type>|<span data-ttu-id="61e0b-110">O texto que você inseriu na caixa de texto **Tipo de fluxo de trabalho** no [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] para identificar qual assembly de fluxo de trabalho personalizado deve ser carregado.</span><span class="sxs-lookup"><span data-stu-id="61e0b-110">The text you entered in the **Workflow type** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] to identify which custom workflow assembly to load.</span></span>|  
|\<SendData>|<span data-ttu-id="61e0b-111">Um valor booliano controlado pela caixa de seleção **Incluir dados de membro na mensagem** no [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61e0b-111">A Boolean value controlled by the **Include member data in the message** checkbox in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="61e0b-112">Um valor de 1 significa que a \<MemberData> seção é enviada; caso contrário, a \<MemberData> seção não é enviada.</span><span class="sxs-lookup"><span data-stu-id="61e0b-112">A value of 1 means that the \<MemberData> section is sent; otherwise the \<MemberData> section is not sent.</span></span>|  
|<span data-ttu-id="61e0b-113"><Server_URL></span><span class="sxs-lookup"><span data-stu-id="61e0b-113"><Server_URL></span></span>|<span data-ttu-id="61e0b-114">O texto que você inseriu na caixa de texto **Site de fluxo de trabalho** no [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61e0b-114">The text you entered in the **Workflow site** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|<span data-ttu-id="61e0b-115"><Action_ID></span><span class="sxs-lookup"><span data-stu-id="61e0b-115"><Action_ID></span></span>|<span data-ttu-id="61e0b-116">O texto que você inseriu na caixa de texto **Nome do fluxo de trabalho** no [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61e0b-116">The text you entered in the **Workflow name** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|\<MemberData>|<span data-ttu-id="61e0b-117">Contém os dados do membro que disparou a ação do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="61e0b-117">Contains the data of the member that triggered the workflow action.</span></span> <span data-ttu-id="61e0b-118">Isso só será incluído se o valor de \<SendData> for 1.</span><span class="sxs-lookup"><span data-stu-id="61e0b-118">This is included only if the value of \<SendData> is 1.</span></span>|  
|\<Enter*xxx*>|<span data-ttu-id="61e0b-119">Esse conjunto de marcas contém metadados sobre a criação do membro, por exemplo, quando foi criado e quem o criou.</span><span class="sxs-lookup"><span data-stu-id="61e0b-119">This set of tags contains metadata about the creation of the member, such as when it was created and who created it.</span></span>|  
|\<LastChg*xxx*>|<span data-ttu-id="61e0b-120">Esse conjunto de marcas contém metadados sobre as últimas alterações feitas no membro, por exemplo, quando a alteração foi feita e quem a fez.</span><span class="sxs-lookup"><span data-stu-id="61e0b-120">This set of tags contains metadata about the last change made to the member, such as when the change was made and who made it.</span></span>|  
|\<Name>|<span data-ttu-id="61e0b-121">O primeiro atributo do membro que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="61e0b-121">The first attribute of the member that was changed.</span></span> <span data-ttu-id="61e0b-122">Este membro de exemplo contém apenas os atributos Name e Code.</span><span class="sxs-lookup"><span data-stu-id="61e0b-122">This example member contains only Name and Code attributes.</span></span>|  
|\<Code>|<span data-ttu-id="61e0b-123">O próximo atributo do membro que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="61e0b-123">The next attribute of the member that was changed.</span></span> <span data-ttu-id="61e0b-124">Se esse membro de exemplo tinha mais atributos, eles viriam depois deste.</span><span class="sxs-lookup"><span data-stu-id="61e0b-124">If this example member contained more attributes, they would follow this one.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61e0b-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="61e0b-125">See Also</span></span>  
 <span data-ttu-id="61e0b-126">[Criar um &#40;de fluxo de trabalho personalizado Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="61e0b-126">[Create a Custom Workflow &#40;Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span></span>  
 [<span data-ttu-id="61e0b-127">Exemplo de fluxo de trabalho personalizado &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="61e0b-127">Custom Workflow Example &#40;Master Data Services&#41;</span></span>](create-a-custom-workflow-example.md)  
  
  
