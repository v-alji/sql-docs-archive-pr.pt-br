---
title: Excluindo dados usando Updategrams XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <after> block
- updategrams [SQLXML], deleting data
- <before> block
- mapping-schema attribute
- record deletions [SQLXML]
ms.assetid: 4fb116d7-7652-474a-a567-cb475a20765c
author: rothja
ms.author: jroth
ms.openlocfilehash: d941005c71dc33dd8c4f5c5cc15f645cd0e68177
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581717"
---
# <a name="deleting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="6b4f3-102">Excluindo dados usando diagramas de atualização XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="6b4f3-102">Deleting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="6b4f3-103">Um updategram indica uma operação de exclusão quando uma instância de registro é exibida no **\<before>** bloco sem registros correspondentes no **\<after>** bloco.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-103">An updategram indicates a delete operation when a record instance appears in the **\<before>** block with no corresponding records in the **\<after>** block.</span></span> <span data-ttu-id="6b4f3-104">Nesse caso, o updategram exclui o registro no **\<before>** bloco do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-104">In this case, the updategram deletes the record in the **\<before>** block from the database.</span></span>  
  
 <span data-ttu-id="6b4f3-105">Este é o formato do diagrama de atualização em uma operação de exclusão:</span><span class="sxs-lookup"><span data-stu-id="6b4f3-105">This is the updategram format for a delete operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
       <ElementName />  
      [<ElementName .../>... ]  
   </updg:before>  
    [<updg:after>  
    </updg:after>]  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="6b4f3-106">Você pode omitir a **\<after>** marca se o updategram estiver executando apenas uma operação de exclusão.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-106">You can omit the **\<after>** tag if the updategram is performing only a delete operation.</span></span> <span data-ttu-id="6b4f3-107">Se você não especificar o atributo opcional `mapping-schema` , o **\<ElementName>** especificado no updategram será mapeado para uma tabela de banco de dados e os elementos filho ou atributos são mapeados para colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-107">If you do not specify the optional `mapping-schema` attribute, the **\<ElementName>** specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
 <span data-ttu-id="6b4f3-108">Se um elemento especificado no updategram corresponder a mais de uma linha na tabela ou não corresponder a nenhuma linha, o updategram retornará um erro e cancelará o **\<sync>** bloco inteiro.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-108">If an element specified in the updategram either matches more than one row in the table or does not match any row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span> <span data-ttu-id="6b4f3-109">Só um registro de cada vez pode ser excluído por um elemento no diagrama.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-109">Only one record at a time can be deleted by an element in the updategram.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6b4f3-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6b4f3-110">Examples</span></span>  
 <span data-ttu-id="6b4f3-111">Os exemplos desta seção usam o mapeamento padrão (ou seja, nenhum esquema de mapeamento é especificado no diagrama de atualização).</span><span class="sxs-lookup"><span data-stu-id="6b4f3-111">Examples in this section use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="6b4f3-112">Para obter mais exemplos de Updategrams que usam esquemas de mapeamento, consulte [especificando um esquema de mapeamento anotado em um Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="6b4f3-112">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="6b4f3-113">Para criar exemplos de trabalho usando os exemplos a seguir, você deve atender aos requisitos especificados em [requisitos para executar exemplos do SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="6b4f3-113">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-deleting-a-record-by-using-an-updategram"></a><span data-ttu-id="6b4f3-114">a.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-114">A.</span></span> <span data-ttu-id="6b4f3-115">Excluindo um registro usando um diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="6b4f3-115">Deleting a record by using an updategram</span></span>  
 <span data-ttu-id="6b4f3-116">Os diagramas a seguir excluem dois registros da tabela HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-116">The following updategrams deletes two records from the HumanResources.Shift table.</span></span>  
  
 <span data-ttu-id="6b4f3-117">Nestes exemplos, o diagrama não especifica um esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-117">In these examples, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="6b4f3-118">Portanto, o diagrama usa o mapeamento padrão no qual o nome de elemento é mapeado para o nome de tabela e os atributos ou subelementos para as colunas.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-118">Therefore, the updategram uses default mapping, in which the element name maps to table name and the attributes or subelements map to columns.</span></span>  
  
 <span data-ttu-id="6b4f3-119">Esse primeiro updategram é centrado em atributo e identifica dois turnos (dia-noite e noite-noturna) no **\<before>** bloco.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-119">This first updategram is attribute-centric and identifies two shifts (Day-Evening and Evening-Night) in the **\<before>** block.</span></span> <span data-ttu-id="6b4f3-120">Como não há nenhum registro correspondente no **\<after>** bloco, essa é uma operação de exclusão.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-120">Because there is no corresponding record in the **\<after>** block, this is a delete operation.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
       <HumanResources.Shift ShiftID="4"  
                        Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift ShiftID="5"  
                        Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:before>  
  <updg:after>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="6b4f3-121">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="6b4f3-121">To test the updategram</span></span>  
  
1.  <span data-ttu-id="6b4f3-122">Conclua o exemplo B ("inserindo vários registros usando um updategram") em [inserindo dados usando os UPDATEGRAMS XML &#40;SQLXML 4,0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="6b4f3-122">Complete example B ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="6b4f3-123">Copie o updategram acima para o bloco de notas e salve-o como Updategram-RemoveShifts.xml na mesma pasta que foi usada para concluir ("inserindo vários registros usando um updategram") na [inserção de dados usando os UPDATEGRAMS XML &#40;SQLXML 4,0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="6b4f3-123">Copy the updategram above to Notepad and save it as Updategram-RemoveShifts.xml in the same folder as was used to complete ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
3.  <span data-ttu-id="6b4f3-124">Crie e use o Script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="6b4f3-124">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="6b4f3-125">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="6b4f3-125">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b4f3-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6b4f3-126">See Also</span></span>  
 [<span data-ttu-id="6b4f3-127">Considerações de segurança do updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6b4f3-127">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
