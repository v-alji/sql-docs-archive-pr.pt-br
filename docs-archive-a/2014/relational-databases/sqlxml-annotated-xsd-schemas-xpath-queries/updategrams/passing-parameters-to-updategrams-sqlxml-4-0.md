---
title: Passando parâmetros para Updategrams (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nullvalue attribute
- passing parameters [SQLXML]
- parameters [SQLXML]
- updategrams [SQLXML], passing parameters
- null values [SQLXML]
ms.assetid: 2354e6e7-1860-471f-8711-4e374c5a4ed2
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bc29de2dab3d0bc3587cb21b7005c0c23dcf7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575744"
---
# <a name="passing-parameters-to-updategrams-sqlxml-40"></a><span data-ttu-id="c653d-102">Transmitindo parâmetros a diagramas de atualização (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c653d-102">Passing Parameters to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="c653d-103">Os diagramas de atualização (updategrams) são modelos; portanto, é possível passar parâmetros para eles.</span><span class="sxs-lookup"><span data-stu-id="c653d-103">Updategrams are templates; therefore, you can pass them parameters.</span></span> <span data-ttu-id="c653d-104">Para obter mais informações sobre como passar parâmetros para modelos, consulte [considerações de segurança do Updategram &#40;SQLXML 4,0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c653d-104">For more information about passing parameters to templates, see [Updategram Security Considerations &#40;SQLXML 4.0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="c653d-105">Diagramas de atualização permitem passar NULL como um valor de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c653d-105">Updategrams allow you to pass NULL as a parameter value.</span></span> <span data-ttu-id="c653d-106">Para passar o valor de parâmetro NULL, você especifica o atributo `nullvalue`.</span><span class="sxs-lookup"><span data-stu-id="c653d-106">To pass the NULL parameter value, you specify the `nullvalue` attribute.</span></span> <span data-ttu-id="c653d-107">O valor atribuído ao atributo `nullvalue` é fornecido como sendo o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c653d-107">The value that is assigned to the `nullvalue` attribute is then provided as the parameter value.</span></span> <span data-ttu-id="c653d-108">Diagramas de atualização tratam esse valor como NULL.</span><span class="sxs-lookup"><span data-stu-id="c653d-108">Updategrams treat this value as NULL.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c653d-109">Em `<sql:header>` e `<updg:header>`, você deve especificar `nullvalue` como não qualificado; enquanto isso, já em `<updg:sync>`, você especifica o `nullvalue` como qualificado (por exemplo, `updg:nullvalue`).</span><span class="sxs-lookup"><span data-stu-id="c653d-109">In `<sql:header>` and `<updg:header>`, you should specify the `nullvalue` as unqualified; whereas, in `<updg:sync>`, you specify the `nullvalue` as qualified (for example, `updg:nullvalue`).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c653d-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="c653d-110">Examples</span></span>  
 <span data-ttu-id="c653d-111">Para criar exemplos de trabalho usando os exemplos a seguir, você deve atender aos requisitos especificados em [requisitos para executar exemplos do SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="c653d-111">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="c653d-112">Antes de usar os exemplos de diagrama de atualização, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c653d-112">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="c653d-113">Os exemplos usam mapeamento padrão (quer dizer, nenhum esquema de mapeamento é especificado no diagrama de atualização).</span><span class="sxs-lookup"><span data-stu-id="c653d-113">The examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="c653d-114">Para obter mais exemplos de Updategrams que usam esquemas de mapeamento, consulte [especificando um esquema de mapeamento anotado em um Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c653d-114">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="a-passing-parameters-to-an-updategram"></a><span data-ttu-id="c653d-115">a.</span><span class="sxs-lookup"><span data-stu-id="c653d-115">A.</span></span> <span data-ttu-id="c653d-116">Passando parâmetros para um diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="c653d-116">Passing parameters to an updategram</span></span>  
 <span data-ttu-id="c653d-117">Neste exemplo, o diagrama de atualização altera o sobrenome de um funcionário na tabela HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="c653d-117">In this example, the updategram changes the last name of an employee in the HumanResources.Shift table.</span></span> <span data-ttu-id="c653d-118">O diagrama de atualização é passado com dois parâmetros: ShiftID, usado para identificar exclusivamente uma troca e Name.</span><span class="sxs-lookup"><span data-stu-id="c653d-118">The updategram is passed two parameters: ShiftID, which is used to uniquely identify a shift, and Name.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header>  
  <updg:param name="ShiftID"/>  
  <updg:param name="Name" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="$ShiftID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="$Name" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="c653d-119">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="c653d-119">To test the updategram</span></span>  
  
1.  <span data-ttu-id="c653d-120">Copie o updategram acima no Bloco de Notas e salve-o em um arquivo como UpdategramWithParameters.xml.</span><span class="sxs-lookup"><span data-stu-id="c653d-120">Copy the updategram above into Notepad and save it to file as UpdategramWithParameters.xml.</span></span>  
  
2.  <span data-ttu-id="c653d-121">Prepare o script de teste do SQLXML 4,0 (Sqlxml4test. vbs) no [usando o ADO para executar consultas do sqlxml 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) para executar o updategram adicionando as seguintes linhas após o `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="c653d-121">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value  
    cmd.Parameters.Append cmd.CreateParameter("@ShiftID",  2, 1,  0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@Name",   200, 1, 50, "New Name")  
    ```  
  
### <a name="b-passing-null-as-a-parameter-value-to-an-updategram"></a><span data-ttu-id="c653d-122">B.</span><span class="sxs-lookup"><span data-stu-id="c653d-122">B.</span></span> <span data-ttu-id="c653d-123">Passando NULL como um valor de parâmetro para um updategram</span><span class="sxs-lookup"><span data-stu-id="c653d-123">Passing NULL as a parameter value to an updategram</span></span>  
 <span data-ttu-id="c653d-124">Na execução de um updategram, o valor "isnull" é atribuído ao parâmetro que você deseja definir como NULL.</span><span class="sxs-lookup"><span data-stu-id="c653d-124">In executing an updategram, the "isnull" value is assigned to the parameter that you want to set to NULL.</span></span> <span data-ttu-id="c653d-125">O diagrama de atualização converte o valor do parâmetro "isnulll" em NULL e o processa de acordo.</span><span class="sxs-lookup"><span data-stu-id="c653d-125">Updategram converts the "isnulll" parameter value to NULL and processes it accordingly.</span></span>  
  
 <span data-ttu-id="c653d-126">O seguinte diagrama de atualização define um cargo de funcionário como NULL:</span><span class="sxs-lookup"><span data-stu-id="c653d-126">The following updategram sets an employee title to NULL:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header nullvalue="isnull" >  
  <updg:param name="EmployeeID"/>  
  <updg:param name="ManagerID" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Employee EmployeeID="$EmployeeID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Employee ManagerID="$ManagerID" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="c653d-127">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="c653d-127">To test the updategram</span></span>  
  
1.  <span data-ttu-id="c653d-128">Copie o diagrama de atualização acima no Bloco de Notas e salve-o em um arquivo como UpdategramPassingNullvalues.xml.</span><span class="sxs-lookup"><span data-stu-id="c653d-128">Copy the updategram above into Notepad and save it to file as UpdategramPassingNullvalues.xml.</span></span>  
  
2.  <span data-ttu-id="c653d-129">Prepare o script de teste do SQLXML 4,0 (Sqlxml4test. vbs) no [usando o ADO para executar consultas do sqlxml 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) para executar o updategram adicionando as seguintes linhas após o `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="c653d-129">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value   
    cmd.Parameters.Append cmd.CreateParameter("@EmployeeID", 3, 1, 0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@ManagerID",  3, 1, 0, Null)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c653d-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c653d-130">See Also</span></span>  
 [<span data-ttu-id="c653d-131">Considerações de segurança do updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c653d-131">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
