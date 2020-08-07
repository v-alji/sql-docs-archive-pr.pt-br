---
title: Atualizando dados usando Updategrams XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREF type attribute [SQLXML]
- before attribute
- <sync> block
- <after> block
- id attribute
- <before> block
- updg:after attribute
- mapping-schema attribute
- IDREFS type attribute [SQLXML]
- updg:id attribute
- multiple record updates
- after attribute
- updategrams [SQLXML], updating data
- updg:before attribute
- record updates [SQLXML]
ms.assetid: 90ef8a33-5ae3-4984-8259-608d2f1d727f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6b019478868b61f293eda824d9b302099728dec4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575741"
---
# <a name="updating-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="d8b43-102">Atualizando dados que usam diagramas de atualização XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d8b43-102">Updating Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="d8b43-103">Ao atualizar os dados existentes, você deve especificar os **\<before>** blocos e **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="d8b43-103">When you update existing data, you must specify both the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="d8b43-104">Os elementos especificados nos **\<before>** blocos e **\<after>** descrevem a alteração desejada.</span><span class="sxs-lookup"><span data-stu-id="d8b43-104">The elements specified in the **\<before>** and **\<after>** blocks describe the desired change.</span></span> <span data-ttu-id="d8b43-105">O updategram usa os elementos que são especificados no **\<before>** bloco para identificar os registros existentes no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d8b43-105">The updategram uses the element(s) that are specified in the **\<before>** block to identify the existing record(s) in the database.</span></span> <span data-ttu-id="d8b43-106">Os elementos correspondentes no **\<after>** bloco indicam como os registros devem ser examinados após a execução da operação de atualização.</span><span class="sxs-lookup"><span data-stu-id="d8b43-106">The corresponding element(s) in the **\<after>** block indicate how the records should look after executing the update operation.</span></span> <span data-ttu-id="d8b43-107">A partir dessas informações, o updategram cria uma instrução SQL que corresponde ao **\<after>** bloco.</span><span class="sxs-lookup"><span data-stu-id="d8b43-107">From this information, the updategram creates an SQL statement that matches the **\<after>** block.</span></span> <span data-ttu-id="d8b43-108">O diagrama de atualização usa esta instrução para atualizar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d8b43-108">The updategram then uses this statement to update the database.</span></span>  
  
 <span data-ttu-id="d8b43-109">Este é o formato do diagrama de atualização para uma operação de atualização:</span><span class="sxs-lookup"><span data-stu-id="d8b43-109">This is the updategram format for an update operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
      <ElementName [updg:id="value"] .../>  
      [<ElementName [updg:id="value"] .../> ... ]  
   </updg:before>  
   <updg:after>  
      <ElementName [updg:id="value"] ... />  
      [<ElementName [updg:id="value"] .../> ...]  
   </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 `<updg:before>`  
 <span data-ttu-id="d8b43-110">Os elementos no **\<before>** bloco identificam os registros existentes nas tabelas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d8b43-110">The elements in the **\<before>** block identify existing records in the database tables.</span></span>  
  
 `<updg:after>`  
 <span data-ttu-id="d8b43-111">Os elementos no **\<after>** bloco descrevem como os registros especificados no **\<before>** bloco devem ser examinados depois que as atualizações são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="d8b43-111">The elements in the **\<after>** block describe how the records specified in the **\<before>** block should look after the updates are applied.</span></span>  
  
 <span data-ttu-id="d8b43-112">O atributo `mapping-schema` identifica o esquema de mapeamento a ser usado pelo diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="d8b43-112">The `mapping-schema` attribute identifies the mapping schema to be used by the updategram.</span></span> <span data-ttu-id="d8b43-113">Se o updategram especificar um esquema de mapeamento, os nomes de elemento e atributo especificados **\<before>** nos **\<after>** blocos e deverão corresponder aos nomes no esquema.</span><span class="sxs-lookup"><span data-stu-id="d8b43-113">If the updategram specifies a mapping schema, the element and attribute names specified in the **\<before>** and **\<after>** blocks must match the names in the schema.</span></span> <span data-ttu-id="d8b43-114">O esquema de mapeamento mapeia esses nomes de elemento ou atributo para os nomes de tabela de banco de dados e de coluna.</span><span class="sxs-lookup"><span data-stu-id="d8b43-114">The mapping schema maps these element or attribute names to the database table and column names.</span></span>  
  
 <span data-ttu-id="d8b43-115">Se um diagrama de atualização não especificar um esquema, o diagrama usará mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="d8b43-115">If an updategram does not specify a schema, the updategam uses default mapping.</span></span> <span data-ttu-id="d8b43-116">No mapeamento padrão, o **\<ElementName>** especificado no updategram mapeia para a tabela de banco de dados e os elementos filho ou atributos são mapeados para as colunas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d8b43-116">In default mapping, the **\<ElementName>** specified in the updategram maps to the database table and the child elements or attributes map to the database columns.</span></span>  
  
 <span data-ttu-id="d8b43-117">Um elemento no **\<before>** bloco deve corresponder a apenas uma linha de tabela no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d8b43-117">An element in the **\<before>** block must match with only one table row in the database.</span></span> <span data-ttu-id="d8b43-118">Se o elemento corresponder a várias linhas da tabela ou não corresponder a nenhuma linha da tabela, o updategram retornará um erro e cancelará o **\<sync>** bloco inteiro.</span><span class="sxs-lookup"><span data-stu-id="d8b43-118">If the element either matches multiple table rows or does not match any table row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span>  
  
 <span data-ttu-id="d8b43-119">Um updategram pode incluir vários **\<sync>** blocos.</span><span class="sxs-lookup"><span data-stu-id="d8b43-119">An updategram can include multiple **\<sync>** blocks.</span></span> <span data-ttu-id="d8b43-120">Cada **\<sync>** bloco é tratado como uma transação.</span><span class="sxs-lookup"><span data-stu-id="d8b43-120">Each **\<sync>** block is treated as a transaction.</span></span> <span data-ttu-id="d8b43-121">Cada **\<sync>** bloco pode ter vários **\<before>** **\<after>** blocos e.</span><span class="sxs-lookup"><span data-stu-id="d8b43-121">Each **\<sync>** block can have multiple **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="d8b43-122">Por exemplo, se você estiver atualizando dois dos registros existentes, poderá especificar dois **\<before>** **\<after>** pares, um para cada registro que está sendo atualizado.</span><span class="sxs-lookup"><span data-stu-id="d8b43-122">For example, if you are updating two of the existing records, you could specify two **\<before>** and **\<after>** pairs, one for each record being updated.</span></span>  
  
## <a name="using-the-updgid-attribute"></a><span data-ttu-id="d8b43-123">Usando o atributo updg:id</span><span class="sxs-lookup"><span data-stu-id="d8b43-123">Using the updg:id Attribute</span></span>  
 <span data-ttu-id="d8b43-124">Quando vários elementos são especificados nos **\<before>** blocos e **\<after>** , use o `updg:id` atributo para marcar linhas nos **\<before>** **\<after>** blocos e.</span><span class="sxs-lookup"><span data-stu-id="d8b43-124">When multiple elements are specified in the **\<before>** and **\<after>** blocks, use the `updg:id` attribute to mark rows in the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="d8b43-125">A lógica de processamento usa essas informações para determinar qual registro nos **\<before>** pares de blocos com qual registro no **\<after>** bloco.</span><span class="sxs-lookup"><span data-stu-id="d8b43-125">The processing logic uses this information to determine what record in the **\<before>** block pairs with what record in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="d8b43-126">O atributo `updg:id` não será necessário (embora recomendado) se alguma das seguintes situações existir:</span><span class="sxs-lookup"><span data-stu-id="d8b43-126">The `updg:id` attribute is not necessary (although recommended) if either of the following exists:</span></span>  
  
-   <span data-ttu-id="d8b43-127">Os elementos no esquema de mapeamento especificado tiverem o atributo `sql:key-fields` definido neles.</span><span class="sxs-lookup"><span data-stu-id="d8b43-127">The elements in the specified mapping schema have the `sql:key-fields` attribute defined on them.</span></span>  
  
-   <span data-ttu-id="d8b43-128">Há um ou mais valor específico fornecido para o campo chave no diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="d8b43-128">There is one or more specific value supplied for the key field(s) in the updategram.</span></span>  
  
 <span data-ttu-id="d8b43-129">Se for o caso, o updategram usará as colunas de chave especificadas no `sql:key-fields` para emparelhar os elementos nos **\<before>** **\<after>** blocos e.</span><span class="sxs-lookup"><span data-stu-id="d8b43-129">If either is the case, the updategram uses the key columns that are specified in the `sql:key-fields` to pair the elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="d8b43-130">Se o esquema de mapeamento não identificar as colunas de chave (usando `sql:key-fields`) ou se o diagrama de atualização estiver atualizando um valor da coluna de chave, você deverá especificar `updg:id`.</span><span class="sxs-lookup"><span data-stu-id="d8b43-130">If the mapping schema does not identify key columns (by using `sql:key-fields`) or if the updategram is updating a key column value, you must specify `updg:id`.</span></span>  
  
 <span data-ttu-id="d8b43-131">Os registros que são identificados nos **\<before>** blocos e **\<after>** não precisam estar na mesma ordem.</span><span class="sxs-lookup"><span data-stu-id="d8b43-131">The records that are identified in the **\<before>** and **\<after>** blocks do not have to be in the same order.</span></span> <span data-ttu-id="d8b43-132">O `updg:id` atributo força a associação entre os elementos que são especificados nos **\<before>** blocos e **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="d8b43-132">The `updg:id` attribute forces the association between the elements that are specified in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="d8b43-133">Se você especificar um elemento no **\<before>** bloco e apenas um elemento correspondente no **\<after>** bloco, o uso do `updg:id` não será necessário.</span><span class="sxs-lookup"><span data-stu-id="d8b43-133">If you specify one element in the **\<before>** block and only one corresponding element in the **\<after>** block, using `updg:id` is not necessary.</span></span> <span data-ttu-id="d8b43-134">Porém, é recomendado que você especifique `updg:id` de qualquer maneira para evitar ambiguidade.</span><span class="sxs-lookup"><span data-stu-id="d8b43-134">However, it is recommended that you specify `updg:id` anyway to avoid ambiguity.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d8b43-135">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d8b43-135">Examples</span></span>  
 <span data-ttu-id="d8b43-136">Antes de você usar os exemplos do diagrama de atualização, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d8b43-136">Before you use the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="d8b43-137">A maioria dos exemplos usa mapeamento padrão (ou seja, nenhum esquema de mapeamento é especificado no diagrama de atualização).</span><span class="sxs-lookup"><span data-stu-id="d8b43-137">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="d8b43-138">Para obter mais exemplos de Updategrams que usam esquemas de mapeamento, consulte [especificando um esquema de mapeamento anotado em um Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="d8b43-138">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="d8b43-139">A maioria dos exemplos usa o banco de dados de exemplo do AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d8b43-139">Most of the examples use the AdventureWorks sample database.</span></span> <span data-ttu-id="d8b43-140">Todas as atualizações são aplicadas às tabelas deste banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d8b43-140">All the updates are applied to the tables in this database.</span></span> <span data-ttu-id="d8b43-141">É possível restaurar o banco de dados AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d8b43-141">You can restore the AdventureWorks database.</span></span>  
  
### <a name="a-updating-a-record"></a><span data-ttu-id="d8b43-142">a.</span><span class="sxs-lookup"><span data-stu-id="d8b43-142">A.</span></span> <span data-ttu-id="d8b43-143">Atualizando um registro</span><span class="sxs-lookup"><span data-stu-id="d8b43-143">Updating a record</span></span>  
 <span data-ttu-id="d8b43-144">O diagrama de atualização a seguir atualiza o sobrenome do funcionário para Silva na tabela Person.Contact no banco de dados do AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d8b43-144">The following updategram updates the employee last name to Fuller in the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="d8b43-145">O diagrama de atualização não especifica nenhum esquema de mapeamento; portanto, o diagrama de atualização usa o mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="d8b43-145">The updategram does not specify any mapping schema; therefore, the updategram uses default mapping.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact LastName="Abel-Achong" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="d8b43-146">O registro descrito no **\<before>** bloco representa o registro atual no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d8b43-146">The record described in the **\<before>** block represents the current record in the database.</span></span> <span data-ttu-id="d8b43-147">O updategram usa todos os valores de coluna especificados no **\<before>** bloco para pesquisar o registro.</span><span class="sxs-lookup"><span data-stu-id="d8b43-147">The updategram uses all of the column values specified in the **\<before>** block to search for the record.</span></span> <span data-ttu-id="d8b43-148">Nesse updategram, o **\<before>** bloco fornece apenas a coluna ContactID; portanto, o updategram usa apenas o valor para pesquisar o registro.</span><span class="sxs-lookup"><span data-stu-id="d8b43-148">In this updategram, the **\<before>** block provides only the ContactID column; therefore, the updategram uses only the value to search for the record.</span></span> <span data-ttu-id="d8b43-149">Se você fosse acrescentar o valor LastName a esse bloco, o diagrama de atualização usaria os valores ContactID e LastName para pesquisar.</span><span class="sxs-lookup"><span data-stu-id="d8b43-149">If you were to add the LastName value to this block, the updategram would use both the ContactID and LastName values to search.</span></span>  
  
 <span data-ttu-id="d8b43-150">Nesse updategram, o **\<after>** bloco fornece apenas o valor de coluna LastName porque esse é o único valor que está sendo alterado.</span><span class="sxs-lookup"><span data-stu-id="d8b43-150">In this updategram, the **\<after>** block provides only the LastName column value because this is the only value that is being changed.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="d8b43-151">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="d8b43-151">To test the updategram</span></span>  
  
1.  <span data-ttu-id="d8b43-152">Copie o modelo de diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d8b43-152">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="d8b43-153">Salve o arquivo como UpdateLastName.xml.</span><span class="sxs-lookup"><span data-stu-id="d8b43-153">Save the file as UpdateLastName.xml.</span></span>  
  
2.  <span data-ttu-id="d8b43-154">Crie e use o Script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="d8b43-154">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="d8b43-155">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d8b43-155">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="b-updating-multiple-records-by-using-the-updgid-attribute"></a><span data-ttu-id="d8b43-156">B.</span><span class="sxs-lookup"><span data-stu-id="d8b43-156">B.</span></span> <span data-ttu-id="d8b43-157">Atualizando vários registros usando o atributo updg:id</span><span class="sxs-lookup"><span data-stu-id="d8b43-157">Updating multiple records by using the updg:id attribute</span></span>  
 <span data-ttu-id="d8b43-158">Neste exemplo, o diagrama de atualização executa duas atualizações na tabela HumanResources.Shift no banco de dados do AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="d8b43-158">In this example, the updategram performs two updates on the HumanResources.Shift table in the AdventureWorks database:</span></span>  
  
-   <span data-ttu-id="d8b43-159">Ele altera o nome do turno do dia original que inicia às 7h00 do "Dia" até a "Madrugada".</span><span class="sxs-lookup"><span data-stu-id="d8b43-159">It changes the name of the original day shift that starts at 7:00AM from "Day" to "Early Morning".</span></span>  
  
-   <span data-ttu-id="d8b43-160">Insere um novo turno denominado "Fim da Manhã" que inicia às 10h00.</span><span class="sxs-lookup"><span data-stu-id="d8b43-160">It inserts a new shift named "Late Morning" that starts at 10:00AM.</span></span>  
  
 <span data-ttu-id="d8b43-161">No updategram, o `updg:id` atributo cria associações entre elementos nos **\<before>** **\<after>** blocos e.</span><span class="sxs-lookup"><span data-stu-id="d8b43-161">In the updategram, the `updg:id` attribute creates associations between elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift updg:id="x" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift updg:id="y" Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
      <HumanResources.Shift updg:id="x" Name="Early Morning" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="d8b43-162">Observe como o `updg:id` atributo emparelha a primeira instância do \<HumanResources.Shift> elemento no **\<before>** bloco com a segunda instância do \<HumanResources.Shift> elemento no **\<after>** bloco.</span><span class="sxs-lookup"><span data-stu-id="d8b43-162">Notice how the `updg:id` attribute pairs the first instance of the \<HumanResources.Shift> element in the **\<before>** block with the second instance of the \<HumanResources.Shift> element in the **\<after>** block.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="d8b43-163">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="d8b43-163">To test the updategram</span></span>  
  
1.  <span data-ttu-id="d8b43-164">Copie o modelo de diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d8b43-164">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="d8b43-165">Salve o arquivo como UpdateMultipleRecords.xml.</span><span class="sxs-lookup"><span data-stu-id="d8b43-165">Save the file as UpdateMultipleRecords.xml.</span></span>  
  
2.  <span data-ttu-id="d8b43-166">Crie e use o Script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="d8b43-166">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="d8b43-167">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d8b43-167">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="c-specifying-multiple-before-and-after-blocks"></a><span data-ttu-id="d8b43-168">C.</span><span class="sxs-lookup"><span data-stu-id="d8b43-168">C.</span></span> <span data-ttu-id="d8b43-169">Especificando vários \<before> \<after> blocos e</span><span class="sxs-lookup"><span data-stu-id="d8b43-169">Specifying multiple \<before> and \<after> blocks</span></span>  
 <span data-ttu-id="d8b43-170">Para evitar ambigüidade, você pode escrever o updategram no exemplo B usando vários **\<before>** **\<after>** pares de blocos e.</span><span class="sxs-lookup"><span data-stu-id="d8b43-170">To avoid ambiguity, you can write the updategram in Example B by using multiple **\<before>** and **\<after>** block pairs.</span></span> <span data-ttu-id="d8b43-171">Especificar **\<before>** **\<after>** pares e é uma maneira de especificar várias atualizações com um mínimo de confusão.</span><span class="sxs-lookup"><span data-stu-id="d8b43-171">Specifying **\<before>** and **\<after>** pairs is one way of specifying multiple updates with a minimum of confusion.</span></span> <span data-ttu-id="d8b43-172">Além disso, se cada um **\<before>** dos **\<after>** blocos e especificar no máximo um elemento, você não precisará usar o `updg:id` atributo.</span><span class="sxs-lookup"><span data-stu-id="d8b43-172">Also, if each of the **\<before>** and **\<after>** blocks specify at most one element, you do not have to use the `updg:id` attribute.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8b43-173">Para formar um par, a **\<after>** marca deve seguir imediatamente sua **\<before>** marca correspondente.</span><span class="sxs-lookup"><span data-stu-id="d8b43-173">To form a pair, the **\<after>** tag must immediately follow its corresponding **\<before>** tag.</span></span>  
  
 <span data-ttu-id="d8b43-174">No updategram a seguir, o primeiro **\<before>** e o **\<after>** par atualiza o nome da mudança para o turno do dia.</span><span class="sxs-lookup"><span data-stu-id="d8b43-174">In the following updategram, the first **\<before>** and **\<after>** pair updates the shift name for the day shift.</span></span> <span data-ttu-id="d8b43-175">O segundo par insere um novo registro de turno.</span><span class="sxs-lookup"><span data-stu-id="d8b43-175">The second pair inserts a new shift record.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Early Morning" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="d8b43-176">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="d8b43-176">To test the updategram</span></span>  
  
1.  <span data-ttu-id="d8b43-177">Copie o modelo de diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d8b43-177">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="d8b43-178">Salve o arquivo como UpdateMultipleBeforeAfter.xml.</span><span class="sxs-lookup"><span data-stu-id="d8b43-178">Save the file as UpdateMultipleBeforeAfter.xml.</span></span>  
  
2.  <span data-ttu-id="d8b43-179">Crie e use o Script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="d8b43-179">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="d8b43-180">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d8b43-180">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-specifying-multiple-sync-blocks"></a><span data-ttu-id="d8b43-181">D.</span><span class="sxs-lookup"><span data-stu-id="d8b43-181">D.</span></span> <span data-ttu-id="d8b43-182">Especificando vários \<sync> blocos</span><span class="sxs-lookup"><span data-stu-id="d8b43-182">Specifying multiple \<sync> blocks</span></span>  
 <span data-ttu-id="d8b43-183">Você pode especificar vários **\<sync>** blocos em um updategram.</span><span class="sxs-lookup"><span data-stu-id="d8b43-183">You can specify multiple **\<sync>** blocks in an updategram.</span></span> <span data-ttu-id="d8b43-184">Cada **\<sync>** bloco especificado é uma transação independente.</span><span class="sxs-lookup"><span data-stu-id="d8b43-184">Each **\<sync>** block that is specified is an independent transaction.</span></span>  
  
 <span data-ttu-id="d8b43-185">No updategram a seguir, o primeiro **\<sync>** bloco atualiza um registro na tabela Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="d8b43-185">In the following updategram, the first **\<sync>** block updates a record in the Sales.Customer table.</span></span> <span data-ttu-id="d8b43-186">Por causa da simplicidade, o diagrama de atualização especifica só os valores de coluna exigidos; o valor de identidade (CustomerID) e o valor que está sendo atualizado (SalesPersonID).</span><span class="sxs-lookup"><span data-stu-id="d8b43-186">For the sake of simplicity, the updategram specifies only the required column values; the identity value (CustomerID) and the value being updated (SalesPersonID).</span></span>  
  
 <span data-ttu-id="d8b43-187">O segundo **\<sync>** bloco adiciona dois registros à tabela Sales. SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="d8b43-187">The second **\<sync>** block adds two records to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="d8b43-188">Para esta tabela, SalesOrderID é uma coluna do IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="d8b43-188">For this table, SalesOrderID is an IDENTITY-type column.</span></span> <span data-ttu-id="d8b43-189">Portanto, o updategram não especifica o valor de SalesOrderID em cada um dos \<Sales.SalesOrderHeader> elementos.</span><span class="sxs-lookup"><span data-stu-id="d8b43-189">Therefore, the updategram does not specify the value of SalesOrderID in each of the \<Sales.SalesOrderHeader> elements.</span></span>  
  
 <span data-ttu-id="d8b43-190">A especificação de vários **\<sync>** blocos é útil porque, se o segundo **\<sync>** bloco (uma transação) falhar ao adicionar registros à tabela Sales. SalesOrderHeader, o primeiro **\<sync>** bloco ainda poderá atualizar o registro do cliente na tabela Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="d8b43-190">Specifying multiple **\<sync>** blocks is useful because if the second **\<sync>** block (a transaction) fails to add records to Sales.SalesOrderHeader table, the first **\<sync>** block can still update the customer record in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
      <Sales.Customer CustomerID="1" SalesPersonID="280" />  
    </updg:before>  
    <updg:after>  
      <Sales.Customer CustomerID="1" SalesPersonID="283" />  
    </updg:after>  
  </updg:sync>  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
   <Sales.SalesOrderHeader   
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="01010101-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-08 00:00:00.000" />  
   <Sales.SalesOrderHeader  
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="1000.0000"  
             TaxAmt="0.0000"  
             Freight="0.0000"  
             rowguid="10101010-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-09 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="d8b43-191">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="d8b43-191">To test the updategram</span></span>  
  
1.  <span data-ttu-id="d8b43-192">Copie o modelo de diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d8b43-192">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="d8b43-193">Salve o arquivo como UpdateMultipleSyncs.xml.</span><span class="sxs-lookup"><span data-stu-id="d8b43-193">Save the file as UpdateMultipleSyncs.xml.</span></span>  
  
2.  <span data-ttu-id="d8b43-194">Crie e use o Script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="d8b43-194">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="d8b43-195">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d8b43-195">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-a-mapping-schema"></a><span data-ttu-id="d8b43-196">E.</span><span class="sxs-lookup"><span data-stu-id="d8b43-196">E.</span></span> <span data-ttu-id="d8b43-197">Usando um esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="d8b43-197">Using a mapping schema</span></span>  
 <span data-ttu-id="d8b43-198">Neste exemplo, o diagrama de atualização especifica um esquema de mapeamento usando o atributo `mapping-schema`.</span><span class="sxs-lookup"><span data-stu-id="d8b43-198">In this example, the updategram specifies a mapping schema by using the `mapping-schema` attribute.</span></span> <span data-ttu-id="d8b43-199">(Não há um mapeamento padrão; isto é, o esquema de mapeamento fornece o mapeamento necessário de elementos e atributos no diagrama de atualização para as tabelas e colunas do banco de dados.)</span><span class="sxs-lookup"><span data-stu-id="d8b43-199">(There is no default mapping; that is, the mapping schema provides the necessary mapping of elements and attributes in the updategram to the database tables and columns.)</span></span>  
  
 <span data-ttu-id="d8b43-200">Os elementos e atributos especificados no diagrama de atualização referem-se aos elementos e atributos no esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="d8b43-200">The elements and attributes specified in the updategram refer to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="d8b43-201">O esquema de mapeamento XSD a seguir tem os **\<Customer>** **\<Order>** elementos, e **\<OD>** que são mapeados para as tabelas Sales. Customer, Sales. SalesOrderHeader e Sales. SalesOrderDetail no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d8b43-201">The following XSD mapping schema has **\<Customer>**, **\<Order>**, and **\<OD>** elements that map to the Sales.Customer, Sales.SalesOrderHeader, and Sales.SalesOrderDetail tables in the database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustomerOrder"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustomerOrder" >  
           <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OD"   
                             sql:relation="Sales.SalesOrderDetail"  
                             sql:relationship="OrderOD" >  
                 <xsd:complexType>  
                  <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                  <xsd:attribute name="ProductID" type="xsd:integer" />  
                  <xsd:attribute name="UnitPrice" type="xsd:decimal" />  
                  <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  <xsd:attribute name="UnitPriceDiscount" type="xsd:decimal" />   
                 </xsd:complexType>  
                </xsd:element>  
              </xsd:sequence>  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
           </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="d8b43-202">Este esquema de mapeamento (UpdategramMappingSchema.xml) é especificado no diagrama de atualização a seguir.</span><span class="sxs-lookup"><span data-stu-id="d8b43-202">This mapping schema (UpdategramMappingSchema.xml) is specified in the following updategram.</span></span> <span data-ttu-id="d8b43-203">O diagrama de atualização adiciona um item de detalhe de ordem na tabela Sales.SalesOrderDetail para uma ordem específica.</span><span class="sxs-lookup"><span data-stu-id="d8b43-203">The updategram adds an order detail item in the Sales.SalesOrderDetail table for a specific order.</span></span> <span data-ttu-id="d8b43-204">O updategram inclui elementos aninhados: um **\<OD>** elemento aninhado dentro de um **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="d8b43-204">The updategram includes nested elements: an **\<OD>** element nested inside an **\<Order>** element.</span></span> <span data-ttu-id="d8b43-205">A relação de chave primária/chave estrangeira entre estes dois elementos é especificada no esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="d8b43-205">The primary key/foreign key relationship between these two elements is specified in the mapping schema.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="UpdategramMappingSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43659" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43659" >  
          <OD ProductID="776" UnitPrice="2329.0000"  
              OrderQty="2" UnitPriceDiscount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="d8b43-206">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="d8b43-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="d8b43-207">Copie o esquema de mapeamento acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d8b43-207">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="d8b43-208">Salve o arquivo como UpdategramMappingSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="d8b43-208">Save the file as UpdategramMappingSchema.xml.</span></span>  
  
2.  <span data-ttu-id="d8b43-209">Copie o modelo de diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d8b43-209">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="d8b43-210">Salve o arquivo como UpdateWithMappingSchema.xml na mesma pasta que foi usada para salvar o esquema de mapeamento (UpdategramMappingSchema.xml).</span><span class="sxs-lookup"><span data-stu-id="d8b43-210">Save the file as UpdateWithMappingSchema.xml in the same folder as was used to save the mapping schema (UpdategramMappingSchema.xml).</span></span>  
  
3.  <span data-ttu-id="d8b43-211">Crie e use o Script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="d8b43-211">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="d8b43-212">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d8b43-212">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="d8b43-213">Para obter mais exemplos de Updategrams que usam esquemas de mapeamento, consulte [especificando um esquema de mapeamento anotado em um Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="d8b43-213">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="f-using-a-mapping-schema-with-idrefs-attributes"></a><span data-ttu-id="d8b43-214">F.</span><span class="sxs-lookup"><span data-stu-id="d8b43-214">F.</span></span> <span data-ttu-id="d8b43-215">Usando um esquema de mapeamento com atributos IDREFS</span><span class="sxs-lookup"><span data-stu-id="d8b43-215">Using a mapping schema with IDREFS attributes</span></span>  
 <span data-ttu-id="d8b43-216">Este exemplo ilustra como os diagramas de atualização usam os atributos IDREFS no esquema de mapeamento para atualizar registros em várias tabelas.</span><span class="sxs-lookup"><span data-stu-id="d8b43-216">This example illustrates how updategrams use the IDREFS attributes in the mapping schema to update records in multiple tables.</span></span> <span data-ttu-id="d8b43-217">Para obter este exemplo, assuma que o banco de dados consiste nas seguintes tabelas:</span><span class="sxs-lookup"><span data-stu-id="d8b43-217">For this example, assume that the database consists of the following tables:</span></span>  
  
-   <span data-ttu-id="d8b43-218">Student(StudentID, LastName)</span><span class="sxs-lookup"><span data-stu-id="d8b43-218">Student(StudentID, LastName)</span></span>  
  
-   <span data-ttu-id="d8b43-219">Course(CourseID, CourseName)</span><span class="sxs-lookup"><span data-stu-id="d8b43-219">Course(CourseID, CourseName)</span></span>  
  
-   <span data-ttu-id="d8b43-220">Enrollment(StudentID, CourseID)</span><span class="sxs-lookup"><span data-stu-id="d8b43-220">Enrollment(StudentID, CourseID)</span></span>  
  
 <span data-ttu-id="d8b43-221">Como um aluno pode se matricular em vários cursos e um curso pode ter muitos alunos, a terceira tabela, Enrollment, é necessária para representar esta relação M:N.</span><span class="sxs-lookup"><span data-stu-id="d8b43-221">Because a student can enroll in many courses and a course can have many students, the third table, the Enrollment table, is required to represent this M:N relationship.</span></span>  
  
 <span data-ttu-id="d8b43-222">O esquema de mapeamento XSD a seguir fornece uma exibição XML das tabelas usando os **\<Student>** **\<Course>** elementos, e **\<Enrollment>** .</span><span class="sxs-lookup"><span data-stu-id="d8b43-222">The following XSD mapping schema provides an XML view of the tables by using the **\<Student>**, **\<Course>**, and **\<Enrollment>** elements.</span></span> <span data-ttu-id="d8b43-223">Os atributos **IDREFS** no esquema de mapeamento especificam a relação entre esses elementos.</span><span class="sxs-lookup"><span data-stu-id="d8b43-223">The **IDREFS** attributes in the mapping schema specify the relationship between these elements.</span></span> <span data-ttu-id="d8b43-224">O atributo **StudentIDList** no **\<Course>** elemento é um atributo de tipo **IDREFS** que se refere à coluna StudentId na tabela de registro.</span><span class="sxs-lookup"><span data-stu-id="d8b43-224">The **StudentIDList** attribute on the **\<Course>** element is an **IDREFS** type attribute that refers to the StudentID column in the Enrollment table.</span></span> <span data-ttu-id="d8b43-225">Da mesma forma, o atributo **Enrollment** no **\<Student>** elemento é um atributo de tipo **IDREFS** que se refere à coluna cursoid na tabela de registro.</span><span class="sxs-lookup"><span data-stu-id="d8b43-225">Likewise, the **EnrolledIn** attribute on the **\<Student>** element is an **IDREFS** type attribute that refers to the CourseID column in the Enrollment table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="StudentEnrollment"  
          parent="Student"  
          parent-key="StudentID"  
          child="Enrollment"  
          child-key="StudentID" />  
  
    <sql:relationship name="CourseEnrollment"  
          parent="Course"  
          parent-key="CourseID"  
          child="Enrollment"  
          child-key="CourseID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Course" sql:relation="Course"   
                             sql:key-fields="CourseID" >  
    <xsd:complexType>  
    <xsd:attribute name="CourseID"  type="xsd:string" />   
    <xsd:attribute name="CourseName"   type="xsd:string" />   
    <xsd:attribute name="StudentIDList" sql:relation="Enrollment"  
                 sql:field="StudentID"  
                 sql:relationship="CourseEnrollment"   
                                     type="xsd:IDREFS" />  
  
    </xsd:complexType>  
  </xsd:element>  
  <xsd:element name="Student" sql:relation="Student" >  
    <xsd:complexType>  
    <xsd:attribute name="StudentID"  type="xsd:string" />   
    <xsd:attribute name="LastName"   type="xsd:string" />   
    <xsd:attribute name="EnrolledIn" sql:relation="Enrollment"  
                 sql:field="CourseID"  
                 sql:relationship="StudentEnrollment"   
                                     type="xsd:IDREFS" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="d8b43-226">Sempre que você especifica este esquema em um diagrama de atualização e insere um registro na tabela Course, o diagrama de atualização insere um novo registro de curso na tabela Course.</span><span class="sxs-lookup"><span data-stu-id="d8b43-226">Whenever you specify this schema in an updategram and insert a record in the Course table, the updategram inserts a new course record in the Course table.</span></span> <span data-ttu-id="d8b43-227">Se você especificar um ou mais novos IDs de aluno para o atributo StudentIDList, o diagrama de atualização também inserirá um registro na tabela Enrollment para cada novo aluno.</span><span class="sxs-lookup"><span data-stu-id="d8b43-227">If you specify one or more new student IDs for the StudentIDList attribute, the updategram also inserts a record in the Enrollment table for the each new student.</span></span> <span data-ttu-id="d8b43-228">O diagrama de atualização garante que nenhuma duplicata seja adicionada à tabela Enrollment.</span><span class="sxs-lookup"><span data-stu-id="d8b43-228">The updategram ensures that no duplicates are added to the Enrollment table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="d8b43-229">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="d8b43-229">To test the updategram</span></span>  
  
1.  <span data-ttu-id="d8b43-230">Crie estas tabelas no banco de dados que é especificado na raiz virtual:</span><span class="sxs-lookup"><span data-stu-id="d8b43-230">Create these tables in the database that is specified in the virtual root:</span></span>  
  
    ```  
    CREATE TABLE Student(StudentID varchar(10) primary key,   
                         LastName varchar(25))  
    CREATE TABLE Course(CourseID varchar(10) primary key,   
                        CourseName varchar(25))  
    CREATE TABLE Enrollment(StudentID varchar(10)   
                                      references Student(StudentID),  
                           CourseID varchar(10)   
                                      references Course(CourseID))  
    ```  
  
2.  <span data-ttu-id="d8b43-231">Adicione estes dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="d8b43-231">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Student VALUES ('S1','Davoli')  
    INSERT INTO Student VALUES ('S2','Fuller')  
  
    INSERT INTO Course VALUES  ('CS101', 'C Programming')  
    INSERT INTO Course VALUES  ('CS102', 'Understanding XML')  
  
    INSERT INTO Enrollment VALUES ('S1', 'CS101')  
    INSERT INTO Enrollment VALUES ('S1', 'CS102')  
    ```  
  
3.  <span data-ttu-id="d8b43-232">Copie o esquema de mapeamento acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d8b43-232">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="d8b43-233">Salve o arquivo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="d8b43-233">Save the file as SampleSchema.xml.</span></span>  
  
4.  <span data-ttu-id="d8b43-234">Salve o diagrama de atualização (SampleUpdategram) na mesma pasta usada para salvar o esquema de mapeamento na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="d8b43-234">Save the updategram (SampleUpdategram) in the same folder used to save the mapping schema in the previous step.</span></span> <span data-ttu-id="d8b43-235">(Esse diagrama de atualização descarta um aluno com StudentID = "1" do curso CS102.)</span><span class="sxs-lookup"><span data-stu-id="d8b43-235">(This updategram drops a student with StudentID="1" from the CS102 course.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="d8b43-236">Crie e use o Script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="d8b43-236">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="d8b43-237">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d8b43-237">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
6.  <span data-ttu-id="d8b43-238">Salve e execute o diagrama de atualização a seguir como descrito nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="d8b43-238">Save and execute the following updategram as described in the previous steps.</span></span> <span data-ttu-id="d8b43-239">O diagrama de atualização adiciona o aluno com StudentID = "1" novamente ao curso CS102 adicionando um registro na tabela Enrollment.</span><span class="sxs-lookup"><span data-stu-id="d8b43-239">The updategram adds the student with StudentID="1" back into the CS102 course by adding a record in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
7.  <span data-ttu-id="d8b43-240">Salve e execute este próximo diagrama de atualização como descrito nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="d8b43-240">Save and execute this next updategram as described in the previous steps.</span></span> <span data-ttu-id="d8b43-241">Esse diagrama de atualização insere três alunos novos e os matricula no curso CS101.</span><span class="sxs-lookup"><span data-stu-id="d8b43-241">This updategram inserts three new students and enrolls them in the CS101 course.</span></span> <span data-ttu-id="d8b43-242">Novamente, a relação de IDREFS insere registros na tabela Enrollment.</span><span class="sxs-lookup"><span data-stu-id="d8b43-242">Again, the IDREFS relationship inserts records in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
           <Course updg:id="y" CourseID="CS101"   
                               CourseName="C Programming" />  
        </updg:before>  
        <updg:after >  
           <Student updg:id="x1" StudentID="S3" LastName="Leverling" />  
           <Student updg:id="x2" StudentID="S4" LastName="Pecock" />  
           <Student updg:id="x3" StudentID="S5" LastName="Buchanan" />  
           <Course updg:id="y" CourseID="CS101"  
                               CourseName="C Programming"  
                               StudentIDList="S3 S4 S5" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
 <span data-ttu-id="d8b43-243">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="d8b43-243">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ElementType name="Enrollment" sql:relation="Enrollment" sql:key-fields="StudentID CourseID">  
    <AttributeType name="StudentID" dt:type="id" />  
    <AttributeType name="CourseID" dt:type="id" />  
  
    <attribute type="StudentID" />  
    <attribute type="CourseID" />  
  </ElementType>  
  <ElementType name="Course" sql:relation="Course" sql:key-fields="CourseID">  
    <AttributeType name="CourseID" dt:type="id" />  
    <AttributeType name="CourseName" />  
  
    <attribute type="CourseID" />  
    <attribute type="CourseName" />  
  
    <AttributeType name="StudentIDList" dt:type="idrefs" />  
    <attribute type="StudentIDList" sql:relation="Enrollment" sql:field="StudentID" >  
        <sql:relationship  
                key-relation="Course"  
                key="CourseID"  
                foreign-relation="Enrollment"  
                foreign-key="CourseID" />  
    </attribute>  
  
  </ElementType>  
  <ElementType name="Student" sql:relation="Student">  
    <AttributeType name="StudentID" dt:type="id" />  
     <AttributeType name="LastName" />  
  
    <attribute type="StudentID" />  
    <attribute type="LastName" />  
  
    <AttributeType name="EnrolledIn" dt:type="idrefs" />  
    <attribute type="EnrolledIn" sql:relation="Enrollment" sql:field="CourseID" >  
        <sql:relationship  
                key-relation="Student"  
                key="StudentID"  
                foreign-relation="Enrollment"  
                foreign-key="StudentID" />  
    </attribute>  
  
    <element type="Enrollment" sql:relation="Enrollment" >  
        <sql:relationship key-relation="Student"  
                          key="StudentID"  
                          foreign-relation="Enrollment"  
                          foreign-key="StudentID" />  
    </element>  
  </ElementType>  
  
</Schema>  
```  
  
 <span data-ttu-id="d8b43-244">Para obter mais exemplos de Updategrams que usam esquemas de mapeamento, consulte [especificando um esquema de mapeamento anotado em um Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="d8b43-244">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b43-245">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d8b43-245">See Also</span></span>  
 [<span data-ttu-id="d8b43-246">Considerações de segurança do updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b43-246">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
