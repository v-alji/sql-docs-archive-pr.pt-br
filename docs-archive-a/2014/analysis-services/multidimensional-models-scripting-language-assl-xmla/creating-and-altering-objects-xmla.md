---
title: Criando e alterando objetos (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [XML for Analysis]
- subordinate objects [XML for Analysis]
- XML for Analysis, objects
- modifying objects
- removing objects
- deleting objects
- XMLA, objects
ms.assetid: a2080867-e130-440c-92eb-f768869f34a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2390c0b921368e7e06f0e5563a7eb59769d99c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582183"
---
# <a name="creating-and-altering-objects-xmla"></a><span data-ttu-id="81401-102">Criando e alterando objetos (XMLA)</span><span class="sxs-lookup"><span data-stu-id="81401-102">Creating and Altering Objects (XMLA)</span></span>
  <span data-ttu-id="81401-103">Os objetos principais podem ser criados, alterados e excluídos de forma independente.</span><span class="sxs-lookup"><span data-stu-id="81401-103">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="81401-104">Os objetos principais incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="81401-104">Major objects include the following objects:</span></span>  
  
-   <span data-ttu-id="81401-105">Servidores</span><span class="sxs-lookup"><span data-stu-id="81401-105">Servers</span></span>  
  
-   <span data-ttu-id="81401-106">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="81401-106">Databases</span></span>  
  
-   <span data-ttu-id="81401-107">Dimensões</span><span class="sxs-lookup"><span data-stu-id="81401-107">Dimensions</span></span>  
  
-   <span data-ttu-id="81401-108">Cubes</span><span class="sxs-lookup"><span data-stu-id="81401-108">Cubes</span></span>  
  
-   <span data-ttu-id="81401-109">Grupos de medidas</span><span class="sxs-lookup"><span data-stu-id="81401-109">Measure groups</span></span>  
  
-   <span data-ttu-id="81401-110">Partições</span><span class="sxs-lookup"><span data-stu-id="81401-110">Partitions</span></span>  
  
-   <span data-ttu-id="81401-111">Perspectivas</span><span class="sxs-lookup"><span data-stu-id="81401-111">Perspectives</span></span>  
  
-   <span data-ttu-id="81401-112">Modelos de mineração</span><span class="sxs-lookup"><span data-stu-id="81401-112">Mining models</span></span>  
  
-   <span data-ttu-id="81401-113">Funções</span><span class="sxs-lookup"><span data-stu-id="81401-113">Roles</span></span>  
  
-   <span data-ttu-id="81401-114">Comandos associados a um servidor ou a um banco de dados</span><span class="sxs-lookup"><span data-stu-id="81401-114">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="81401-115">Fontes de dados</span><span class="sxs-lookup"><span data-stu-id="81401-115">Data sources</span></span>  
  
 <span data-ttu-id="81401-116">Você usa o comando [Create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) para criar um objeto principal em uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e o comando [ALTER](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) para alterar um objeto principal existente em uma instância.</span><span class="sxs-lookup"><span data-stu-id="81401-116">You use the [Create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) command to create a major object on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], and the [Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) command to alter an existing major object on an instance.</span></span> <span data-ttu-id="81401-117">Ambos os comandos são executados usando o método [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) .</span><span class="sxs-lookup"><span data-stu-id="81401-117">Both commands are run using the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="81401-118">Criando objetos</span><span class="sxs-lookup"><span data-stu-id="81401-118">Creating Objects</span></span>  
 <span data-ttu-id="81401-119">Quando você cria objetos usando o método `Create`, primeiro deve identificar o objeto pai que contém o objeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a ser criado.</span><span class="sxs-lookup"><span data-stu-id="81401-119">When you create objects by using the `Create` method, you must first identify the parent object that contains the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object to be created.</span></span> <span data-ttu-id="81401-120">Você identifica o objeto pai fornecendo uma referência de objeto na propriedade [ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) do `Create` comando.</span><span class="sxs-lookup"><span data-stu-id="81401-120">You identify the parent object by providing an object reference in the [ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Create` command.</span></span> <span data-ttu-id="81401-121">Cada referência de objeto contém os identificadores de objetos necessários para a identificação exclusiva do objeto pai para o comando `Create`.</span><span class="sxs-lookup"><span data-stu-id="81401-121">Each object reference contains the object identifiers needed to uniquely identify the parent object for the `Create` command.</span></span> <span data-ttu-id="81401-122">Para obter mais informações sobre referências de objeto, consulte [definindo e identificando objetos &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="81401-122">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="81401-123">Por exemplo, você deve fornecer uma referência de objeto a um cubo para criar um grupo de medidas novo para ele.</span><span class="sxs-lookup"><span data-stu-id="81401-123">For example, you must provide an object reference to a cube to create a new measure group for the cube.</span></span> <span data-ttu-id="81401-124">A referência de objeto para o cubo na propriedade `ParentObject` contém um identificador de banco de dados e um identificador de cubo, já que, potencialmente, o mesmo identificador de cubo poderia ser usado em um banco de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="81401-124">The object reference for the cube in the `ParentObject` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="81401-125">O elemento [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) contém Analysis Services elementos de linguagem de script (ASSL) que definem o objeto principal a ser criado.</span><span class="sxs-lookup"><span data-stu-id="81401-125">The [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) element contains Analysis Services Scripting Language (ASSL) elements that define the major object to be created.</span></span> <span data-ttu-id="81401-126">Para obter mais informações sobre o ASSL, consulte [desenvolvendo com a linguagem de script Analysis Services &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="81401-126">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="81401-127">Se você definir o atributo `AllowOverwrite` do comando `Create` como verdadeiro, poderá substituir um objeto principal existente que tenha o identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="81401-127">If you set the `AllowOverwrite` attribute of the `Create` command to true, you can overwrite an existing major object that has the specified identifier.</span></span> <span data-ttu-id="81401-128">Caso contrário, ocorrerá um erro se um objeto principal com o identificador especificado já existir no objeto pai.</span><span class="sxs-lookup"><span data-stu-id="81401-128">Otherwise, an error occurs if a major object that has the specified identifier already exists in the parent object.</span></span>  
  
 <span data-ttu-id="81401-129">Para obter mais informações sobre o `Create` comando, consulte [criar elemento &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="81401-129">For more information about the `Create` command, see [Create Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span></span>  
  
### <a name="creating-session-objects"></a><span data-ttu-id="81401-130">Criando objetos de sessão</span><span class="sxs-lookup"><span data-stu-id="81401-130">Creating Session Objects</span></span>  
 <span data-ttu-id="81401-131">Os objetos de sessão são objetos temporários que só estão disponíveis para a sessão explícita ou implícita usada por um aplicativo cliente e são excluídos quando a sessão é encerrada.</span><span class="sxs-lookup"><span data-stu-id="81401-131">Session objects are temporary objects that are available only to the explicit or implicit session used by a client application and are deleted when the session is ended.</span></span> <span data-ttu-id="81401-132">Você pode criar objetos de sessão definindo o `Scope` atributo do `Create` comando para *sessão*.</span><span class="sxs-lookup"><span data-stu-id="81401-132">You can create session objects by setting the `Scope` attribute of the `Create` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81401-133">Ao usar a configuração de *sessão* , o `ObjectDefinition` elemento só pode conter elementos de [dimensão](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [cubo](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)ou [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL.</span><span class="sxs-lookup"><span data-stu-id="81401-133">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="altering-objects"></a><span data-ttu-id="81401-134">Alterando objetos</span><span class="sxs-lookup"><span data-stu-id="81401-134">Altering Objects</span></span>  
 <span data-ttu-id="81401-135">Ao modificar objetos usando o `Alter` método, primeiro você deve identificar o objeto a ser modificado fornecendo uma referência de objeto na propriedade [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) do `Alter` comando.</span><span class="sxs-lookup"><span data-stu-id="81401-135">When modifying objects by using the `Alter` method, you must first identify the object to be modified by providing an object reference in the [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Alter` command.</span></span> <span data-ttu-id="81401-136">Cada referência de objeto contém os identificadores de objetos necessários para a identificação exclusiva do objeto para o comando `Alter`.</span><span class="sxs-lookup"><span data-stu-id="81401-136">Each object reference contains the object identifiers needed to uniquely identify the object for the `Alter` command.</span></span> <span data-ttu-id="81401-137">Para obter mais informações sobre referências de objeto, consulte [definindo e identificando objetos &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="81401-137">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="81401-138">Por exemplo, você deve fornecer uma referência de objeto a um cubo para modificar a sua estrutura.</span><span class="sxs-lookup"><span data-stu-id="81401-138">For example, you must provide an object reference to a cube in order to modify the structure of a cube.</span></span> <span data-ttu-id="81401-139">A referência de objeto para o cubo na propriedade `Object` contém um identificador de banco de dados e um identificador de cubo, já que, potencialmente, o mesmo identificador de cubo poderia ser usado em um banco de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="81401-139">The object reference for the cube in the `Object` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="81401-140">O elemento `ObjectDefinition` contém elementos da ASSL que definem o objeto principal a ser modificado.</span><span class="sxs-lookup"><span data-stu-id="81401-140">The `ObjectDefinition` element contains ASSL elements that define the major object to be modified.</span></span> <span data-ttu-id="81401-141">Para obter mais informações sobre o ASSL, consulte [desenvolvendo com a linguagem de script Analysis Services &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="81401-141">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="81401-142">Se você definir o atributo `AllowCreate` do comando `Alter` como verdadeiro, poderá criar o um objeto principal especificado caso ele ainda não exista.</span><span class="sxs-lookup"><span data-stu-id="81401-142">If you set the `AllowCreate` attribute of the `Alter` command to true, you can create the specified major object if the object does not exist.</span></span> <span data-ttu-id="81401-143">Caso contrário, ocorrerá um erro se um objeto principal especificado ainda não existir.</span><span class="sxs-lookup"><span data-stu-id="81401-143">Otherwise, an error occurs if a specified major object does not already exist.</span></span>  
  
### <a name="using-the-objectexpansion-attribute"></a><span data-ttu-id="81401-144">Usando o atributo ObjectExpansion</span><span class="sxs-lookup"><span data-stu-id="81401-144">Using the ObjectExpansion Attribute</span></span>  
 <span data-ttu-id="81401-145">Se você estiver alterando apenas as propriedades do objeto principal e não estiver redefinindo objetos secundários contidos pelo objeto principal, poderá definir o `ObjectExpansion` atributo do `Alter` comando para *ObjectProperties*.</span><span class="sxs-lookup"><span data-stu-id="81401-145">If you are changing only the properties of the major object and are not redefining minor objects that are contained by the major object, you can set the `ObjectExpansion` attribute of the `Alter` command to *ObjectProperties*.</span></span> <span data-ttu-id="81401-146">A propriedade `ObjectDefinition` só precisará conter os elementos para as propriedades do objeto principal, e o comando `Alter` não tocará nos objetos secundários associados ao objeto principal.</span><span class="sxs-lookup"><span data-stu-id="81401-146">The `ObjectDefinition` property then only has to contain the elements for the properties of the major object, and the `Alter` command leaves minor objects associated with the major object untouched.</span></span>  
  
 <span data-ttu-id="81401-147">Para redefinir objetos secundários para um objeto principal, você deve definir o `ObjectExpansion` atributo como *ExpandFull* e a definição do objeto deve incluir todos os objetos secundários contidos pelo objeto principal.</span><span class="sxs-lookup"><span data-stu-id="81401-147">To redefine minor objects for a major object, you must set the `ObjectExpansion` attribute to *ExpandFull* and the object definition must include all minor objects that are contained by the major object.</span></span> <span data-ttu-id="81401-148">Se a propriedade `ObjectDefinition` do comando `Alter` não incluir explicitamente um objeto secundário contido pelo objeto principal, esse objeto secundário será excluído.</span><span class="sxs-lookup"><span data-stu-id="81401-148">If the `ObjectDefinition` property of the `Alter` command does not explicitly include a minor object that is contained by the major object, the minor object that was not included is deleted.</span></span>  
  
### <a name="altering-session-objects"></a><span data-ttu-id="81401-149">Alterando objetos de sessão</span><span class="sxs-lookup"><span data-stu-id="81401-149">Altering Session Objects</span></span>  
 <span data-ttu-id="81401-150">Para modificar objetos de sessão criados pelo `Create` comando, defina o `Scope` atributo do `Alter` comando para *sessão*.</span><span class="sxs-lookup"><span data-stu-id="81401-150">To modify session objects created by the `Create` command, set the `Scope` attribute of the `Alter` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81401-151">Ao usar a configuração de *sessão* , o `ObjectDefinition` elemento só pode conter elementos de [dimensão](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [cubo](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)ou [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL.</span><span class="sxs-lookup"><span data-stu-id="81401-151">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="creating-or-altering-subordinate-objects"></a><span data-ttu-id="81401-152">Criando ou alterando objetos subordinados</span><span class="sxs-lookup"><span data-stu-id="81401-152">Creating or Altering Subordinate Objects</span></span>  
 <span data-ttu-id="81401-153">Embora um comando `Create` ou `Alter` crie ou altere somente o objeto principal superior, o objeto principal criado ou modificado poderá conter definições na propriedade de circunscrição `ObjectDefinition` para outros objetos principais e secundários subordinados a ele.</span><span class="sxs-lookup"><span data-stu-id="81401-153">Although a `Create` or `Alter` command creates or alters only one topmost major object, the major object being created or modified can contain definitions within the enclosing `ObjectDefinition` property for other major and minor objects that are subordinate to it.</span></span> <span data-ttu-id="81401-154">Por exemplo, se você definir um cubo, especificará o banco de dados pai em `ParentObject`, na definição do cubo em `ObjectDefinition`, você poderá definir grupos de medidas para o cubo e no grupo de medidas poderá definir partições para cada grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="81401-154">For example, if you define a cube, you specify the parent database in `ParentObject`, and within the cube definition in `ObjectDefinition` you can define measure groups for the cube, and within the measure groups you can define partitions for each measure group.</span></span> <span data-ttu-id="81401-155">Um objeto secundário só pode ser definido sob o objeto principal que o contém.</span><span class="sxs-lookup"><span data-stu-id="81401-155">A minor object can be defined only under the major object that contains it.</span></span> <span data-ttu-id="81401-156">Para obter mais informações sobre objetos principais e secundários, consulte [objetos de banco de dados &#40;Analysis Services-&#41;multidimensional ](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="81401-156">For more information about major and minor objects, see [Database Objects &#40;Analysis Services - Multidimensional Data&#41;](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="81401-157">Exemplos</span><span class="sxs-lookup"><span data-stu-id="81401-157">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="81401-158">Descrição</span><span class="sxs-lookup"><span data-stu-id="81401-158">Description</span></span>  
 <span data-ttu-id="81401-159">O exemplo a seguir cria uma fonte de dados relacional que faz referência ao banco de dado de [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] exemplo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81401-159">The following example creates a relational data source that references the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="81401-160">Código</span><span class="sxs-lookup"><span data-stu-id="81401-160">Code</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    </ParentObject>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ImpersonationInfo>  
                <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
            </ImpersonationInfo>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT0S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Create>  
```  
  
### <a name="description"></a><span data-ttu-id="81401-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="81401-161">Description</span></span>  
 <span data-ttu-id="81401-162">O exemplo a seguir altera a fonte de dados relacional criada no exemplo anterior para definir o tempo limite da consulta para a fonte de dados como 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="81401-162">The following example alters the relational data source created in the previous example to set the query time-out for the data source to 30 seconds.</span></span>  
  
### <a name="code"></a><span data-ttu-id="81401-163">Código</span><span class="sxs-lookup"><span data-stu-id="81401-163">Code</span></span>  
  
```  
<Alter ObjectExpansion="ObjectProperties" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DataSourceID>AdventureWorksDW2012</DataSourceID>  
    </Object>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=fr-dwk-02;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT30S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Alter>  
```  
  
### <a name="comments"></a><span data-ttu-id="81401-164">Comentários</span><span class="sxs-lookup"><span data-stu-id="81401-164">Comments</span></span>  
 <span data-ttu-id="81401-165">O `ObjectExpansion` atributo do `Alter` comando foi definido como *ObjectProperties*.</span><span class="sxs-lookup"><span data-stu-id="81401-165">The `ObjectExpansion` attribute of the `Alter` command was set to *ObjectProperties*.</span></span> <span data-ttu-id="81401-166">Essa configuração permite que o elemento [ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) , um objeto secundário, seja excluído da fonte de dados definida em `ObjectDefinition` .</span><span class="sxs-lookup"><span data-stu-id="81401-166">This setting allows the [ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) element, a minor object, to be excluded from the data source defined in `ObjectDefinition`.</span></span> <span data-ttu-id="81401-167">Dessa forma, a informações de representação para aquela fonte de dados permanece definida para a conta de serviço, como especificado no primeiro exemplo.</span><span class="sxs-lookup"><span data-stu-id="81401-167">Therefore, the impersonation information for that data source remains set to the service account, as specified in the first example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81401-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81401-168">See Also</span></span>  
 <span data-ttu-id="81401-169">[Método execute &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span><span class="sxs-lookup"><span data-stu-id="81401-169">[Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span></span>  
 <span data-ttu-id="81401-170">[Desenvolvendo com a linguagem de script Analysis Services &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span><span class="sxs-lookup"><span data-stu-id="81401-170">[Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span></span>  
 [<span data-ttu-id="81401-171">Desenvolvendo com XMLA no Analysis Services</span><span class="sxs-lookup"><span data-stu-id="81401-171">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
