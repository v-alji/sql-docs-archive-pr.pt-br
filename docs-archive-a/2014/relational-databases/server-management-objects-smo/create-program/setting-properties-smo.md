---
title: Definindo propriedades | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SMO [SQL Server], properties
- SQL Server Management Objects, properties
- properties [SMO]
ms.assetid: 342569ba-d2f7-44d2-8f3f-ae9c701c7f0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: de381f8e4e9dfe9f6590638742e988f866ccabdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682204"
---
# <a name="setting-properties"></a><span data-ttu-id="80e34-102">Definindo propriedades</span><span class="sxs-lookup"><span data-stu-id="80e34-102">Setting Properties</span></span>
  <span data-ttu-id="80e34-103">Propriedades são valores que armazenam informações descritivas sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="80e34-103">Properties are values that store descriptive information about the object.</span></span> <span data-ttu-id="80e34-104">Por exemplo, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as opções de configuração são representadas pelas <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> Propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="80e34-104">For example, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] configuration options are represented by the <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> object's properties.</span></span> <span data-ttu-id="80e34-105">As propriedades podem ser acessadas direta ou indiretamente por meio da coleção de propriedades.</span><span class="sxs-lookup"><span data-stu-id="80e34-105">Properties can be accessed either directly or indirectly by using the property collection.</span></span> <span data-ttu-id="80e34-106">O acesso direto às propriedades usa a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="80e34-106">Accessing properties directly uses the following syntax:</span></span>  
  
 `objInstance.PropertyName`  
  
 <span data-ttu-id="80e34-107">Um valor de propriedade pode ser modificado ou recuperado dependendo do tipo de acesso que tem a propriedade, ou seja, acesso de leitura/gravação ou acesso somente leitura.</span><span class="sxs-lookup"><span data-stu-id="80e34-107">A property value can be modified or retrieved depending on whether the property has read/write access or read-only access.</span></span> <span data-ttu-id="80e34-108">Também é necessário definir certas propriedades antes que um objeto possa ser criado.</span><span class="sxs-lookup"><span data-stu-id="80e34-108">It is also necessary to set certain properties before an object can be created.</span></span> <span data-ttu-id="80e34-109">Para obter mais informações, consulte a referência SMO para o objeto em particular.</span><span class="sxs-lookup"><span data-stu-id="80e34-109">For more information, see the SMO reference for the particular object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80e34-110">Coleções de objetos filho aparecem como a propriedade de um objeto.</span><span class="sxs-lookup"><span data-stu-id="80e34-110">Collections of child objects appear as the property of an object.</span></span> <span data-ttu-id="80e34-111">Por exemplo, a coleção `Tables` é uma propriedade de um objeto `Server`.</span><span class="sxs-lookup"><span data-stu-id="80e34-111">For example, the `Tables` collection is a property of a `Server` object.</span></span> <span data-ttu-id="80e34-112">Para obter mais informações, consulte [Using Collections](using-collections.md).</span><span class="sxs-lookup"><span data-stu-id="80e34-112">For more information, see [Using Collections](using-collections.md).</span></span>  
  
 <span data-ttu-id="80e34-113">As propriedades de um objeto são membros da coleção Properties.</span><span class="sxs-lookup"><span data-stu-id="80e34-113">The properties of an object are members of the Properties collection.</span></span> <span data-ttu-id="80e34-114">A coleção Properties pode ser usada para iterar por cada propriedade de um objeto.</span><span class="sxs-lookup"><span data-stu-id="80e34-114">The Properties collection can be used to iterate through every property of an object.</span></span>  
  
 <span data-ttu-id="80e34-115">Às vezes, uma propriedade não está disponível pelas seguintes razões:</span><span class="sxs-lookup"><span data-stu-id="80e34-115">Sometimes a property is not available for the following reasons:</span></span>  
  
-   <span data-ttu-id="80e34-116">A versão do servidor não suporta a propriedade, como se você tentasse acessar uma propriedade que representasse um novo recurso do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] em uma versão mais antiga do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80e34-116">The server version does not support the property, such as if you try to access a property that represents a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] feature on an older version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="80e34-117">O servidor não dá suporte a dados para a propriedade, como se você tentasse acessar uma propriedade que representasse um componente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que não está instalado.</span><span class="sxs-lookup"><span data-stu-id="80e34-117">The server does not provide data for the property, such as if you try to access a property that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] component that is not installed.</span></span>  
  
 <span data-ttu-id="80e34-118">Você pode lidar com essas situações capturando as exceções do SMO <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> e <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException>.</span><span class="sxs-lookup"><span data-stu-id="80e34-118">You can handle these circumstances by catching the <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> and the <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException> SMO exceptions.</span></span>  
  
## <a name="setting-default-initialization-fields"></a><span data-ttu-id="80e34-119">Definindo campos de inicialização padrão</span><span class="sxs-lookup"><span data-stu-id="80e34-119">Setting Default Initialization Fields</span></span>  
 <span data-ttu-id="80e34-120">O SMO executa uma otimização ao recuperar objetos.</span><span class="sxs-lookup"><span data-stu-id="80e34-120">SMO performs an optimization when retrieving objects.</span></span> <span data-ttu-id="80e34-121">A otimização minimiza o número de propriedades carregado, dimensionando automaticamente entre os seguintes estados:</span><span class="sxs-lookup"><span data-stu-id="80e34-121">The optimization minimizes the number of properties loaded by automatically scaling between the following states:</span></span>  
  
1.  <span data-ttu-id="80e34-122">Parcialmente carregado.</span><span class="sxs-lookup"><span data-stu-id="80e34-122">Partially loaded.</span></span> <span data-ttu-id="80e34-123">Quando um objeto é referenciado pela primeira vez, ele tem um mínimo de propriedades disponíveis (como Nome e Esquema).</span><span class="sxs-lookup"><span data-stu-id="80e34-123">When an object is first referenced it has a minimum of properties available (such as Name and Schema).</span></span>  
  
2.  <span data-ttu-id="80e34-124">Completamente carregado.</span><span class="sxs-lookup"><span data-stu-id="80e34-124">Fully loaded.</span></span> <span data-ttu-id="80e34-125">Quando qualquer propriedade é referenciada, as propriedades restantes de carregamento rápido são inicializadas e disponibilizadas.</span><span class="sxs-lookup"><span data-stu-id="80e34-125">When any property is referenced, the remaining properties that are quick to load, are initialized and are made available.</span></span>  
  
3.  <span data-ttu-id="80e34-126">Propriedades que consomem muita memória.</span><span class="sxs-lookup"><span data-stu-id="80e34-126">Properties that use lots of memory.</span></span> <span data-ttu-id="80e34-127">As propriedades indisponíveis restantes consomem muita memória e têm um valor de propriedade <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> definido como verdadeiro (como <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span><span class="sxs-lookup"><span data-stu-id="80e34-127">The remaining unavailable properties use lots of memory and have an <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> property value of true (such as <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span></span> <span data-ttu-id="80e34-128">Essas propriedades só são carregadas quando especificamente referenciadas.</span><span class="sxs-lookup"><span data-stu-id="80e34-128">These properties are loaded only when specifically referenced.</span></span>  
  
 <span data-ttu-id="80e34-129">Se seu aplicativo busca outras propriedades, além daquelas fornecidas no estado parcialmente carregado, ele envia uma consulta para recuperar essas propriedades extras e sobe para o estado totalmente carregado.</span><span class="sxs-lookup"><span data-stu-id="80e34-129">If your application does fetch extra properties, besides the ones provided in the partially loaded state, it submits a query to retrieve these extra properties and scales up to the fully loaded state.</span></span> <span data-ttu-id="80e34-130">Isso pode gerar um tráfego desnecessário entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="80e34-130">This can cause unnecessary traffic between the client and server.</span></span> <span data-ttu-id="80e34-131">Para obter mais otimização, chame o método <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A>.</span><span class="sxs-lookup"><span data-stu-id="80e34-131">More optimization can be achieved by calling the <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method.</span></span> <span data-ttu-id="80e34-132">O método <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> permite a especificação das propriedades que são carregadas quando o objeto é inicializado.</span><span class="sxs-lookup"><span data-stu-id="80e34-132">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method allows specification of the properties that are loaded when the object is initialized.</span></span>  
  
 <span data-ttu-id="80e34-133">O método <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> define o comportamento de carregamento da propriedade para o restante do aplicativo ou até que ele seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="80e34-133">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method sets the property loading behavior for the rest of application or until it is reset.</span></span> <span data-ttu-id="80e34-134">Você pode salvar o comportamento original usando o método <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> e pode restaurá-lo conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="80e34-134">You can save the original behavior by using the <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> method and restore it as required.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="80e34-135">Exemplos</span><span class="sxs-lookup"><span data-stu-id="80e34-135">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="getting-and-setting-a-property-in-visual-basic"></a><span data-ttu-id="80e34-136">Obtendo e configurando uma propriedade no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80e34-136">Getting and Setting a Property in Visual Basic</span></span>  
 <span data-ttu-id="80e34-137">Este exemplo de código mostra como obter a propriedade <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Information> e como definir a propriedade <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> da propriedade <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> como o membro `ExecuteSql` do tipo enumerado <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>.</span><span class="sxs-lookup"><span data-stu-id="80e34-137">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties1](SMO How to#SMO_VBProperties1)]  -->  
  
## <a name="getting-and-setting-a-property-in-visual-c"></a><span data-ttu-id="80e34-138">Obtendo e configurando uma propriedade no Visual C#</span><span class="sxs-lookup"><span data-stu-id="80e34-138">Getting and Setting a Property in Visual C#</span></span>  
 <span data-ttu-id="80e34-139">Este exemplo de código mostra como obter a propriedade <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Information> e como definir a propriedade <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> da propriedade <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> como o membro `ExecuteSql` do tipo enumerado <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>.</span><span class="sxs-lookup"><span data-stu-id="80e34-139">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Get a property.   
Console.WriteLine(srv.Information.Version);   
//Set a property.   
srv.ConnectionContext.SqlExecutionModes = SqlExecutionModes.ExecuteSql;   
}  
```  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-basic"></a><span data-ttu-id="80e34-140">Definindo várias propriedades antes de um objeto ser criado no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80e34-140">Setting Various Properties Before an Object is Created in Visual Basic</span></span>  
 <span data-ttu-id="80e34-141">Este exemplo de código mostra como definir diretamente a propriedade <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Table>, e como criar e adicionar colunas antes de criar o objeto <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="80e34-141">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties2](SMO How to#SMO_VBProperties2)]  -->  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-c"></a><span data-ttu-id="80e34-142">Definindo várias propriedades antes de um objeto ser criado no Visual C#</span><span class="sxs-lookup"><span data-stu-id="80e34-142">Setting Various Properties Before an Object is Created in Visual C#</span></span>  
 <span data-ttu-id="80e34-143">Este exemplo de código mostra como definir diretamente a propriedade <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Table>, e como criar e adicionar colunas antes de criar o objeto <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="80e34-143">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Create a new table in the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
Table tb;   
//Specify the parent database, table schema, and the table name in the constructor.   
tb = new Table(db, "Test_Table", "HumanResources");   
//Add columns because the table requires columns before it can be created.   
Column c1;   
//Specify the parent table, the column name, and data type in the constructor.   
c1 = new Column(tb, "ID", DataType.Int);   
tb.Columns.Add(c1);   
c1.Nullable = false;   
c1.Identity = true;   
c1.IdentityIncrement = 1;   
c1.IdentitySeed = 0;   
Column c2;   
c2 = new Column(tb, "Name", DataType.NVarChar(100));   
c2.Nullable = false;   
tb.Columns.Add(c2);   
tb.AnsiNullsStatus = true;   
//Create the table on the instance of SQL Server.   
tb.Create();   
}  
```  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-basic"></a><span data-ttu-id="80e34-144">Iterando por todas as propriedades de um objeto no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80e34-144">Iterating Through All Properties of an Object in Visual Basic</span></span>  
 <span data-ttu-id="80e34-145">Este exemplo de código itera pela coleção `Properties` do objeto <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> e a exibe na tela Saída do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80e34-145">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
 <span data-ttu-id="80e34-146">No exemplo, o objeto <xref:Microsoft.SqlServer.Management.Smo.Property> foi colocado entre colchetes porque também é uma palavra-chave do [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80e34-146">In the example, the <xref:Microsoft.SqlServer.Management.Smo.Property> object has been put in square parentheses because it is also a [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] keyword.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties3](SMO How to#SMO_VBProperties3)]  -->  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-c"></a><span data-ttu-id="80e34-147">Iterando por todas as propriedades de um objeto no Visual C#</span><span class="sxs-lookup"><span data-stu-id="80e34-147">Iterating Through All Properties of an Object in Visual C#</span></span>  
 <span data-ttu-id="80e34-148">Este exemplo de código itera pela coleção `Properties` do objeto <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> e a exibe na tela Saída do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80e34-148">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Set properties on the uspGetEmployeedManagers stored procedure on the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
StoredProcedure sp;   
sp = db.StoredProcedures("uspGetEmployeeManagers");   
sp.AnsiNullsStatus = false;   
sp.QuotedIdentifierStatus = false;   
//Iterate through the properties of the stored procedure and display.   
  Property p;   
  foreach ( p in sp.Properties) {   
    Console.WriteLine(p.Name + p.Value);   
  }   
}  
```  
  
## <a name="setting-default-initialization-fields-in-visual-basic"></a><span data-ttu-id="80e34-149">Definindo campos de inicialização padrão no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80e34-149">Setting Default Initialization Fields in Visual Basic</span></span>  
 <span data-ttu-id="80e34-150">Este exemplo de código mostra como minimizar o número de propriedades de objeto inicializadas em um programa de SMO.</span><span class="sxs-lookup"><span data-stu-id="80e34-150">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="80e34-151">Você tem de incluir a instrução `using System.Collections.Specialized`; para usar o objeto <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="80e34-151">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 <span data-ttu-id="80e34-152">O [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] pode ser usado para comparar as instruções de número enviadas à instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] com esta otimização.</span><span class="sxs-lookup"><span data-stu-id="80e34-152">[!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDefaultInitFields1](SMO How to#SMO_VBDefaultInitFields1)]  -->  
  
## <a name="setting-default-initialization-fields-in-visual-c"></a><span data-ttu-id="80e34-153">Definindo campos de inicialização padrão no Visual C#</span><span class="sxs-lookup"><span data-stu-id="80e34-153">Setting Default Initialization Fields in Visual C#</span></span>  
 <span data-ttu-id="80e34-154">Este exemplo de código mostra como minimizar o número de propriedades de objeto inicializadas em um programa de SMO.</span><span class="sxs-lookup"><span data-stu-id="80e34-154">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="80e34-155">Você tem de incluir a instrução `using System.Collections.Specialized`; para usar o objeto <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="80e34-155">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 <span data-ttu-id="80e34-156">O [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] pode ser usado para comparar as instruções de número enviadas à instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] com esta otimização.</span><span class="sxs-lookup"><span data-stu-id="80e34-156">[!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Assign the Table object type to a System.Type object variable.   
Table tb;   
Type typ;   
tb = new Table();   
typ = tb.GetType;   
//Assign the current default initialization fields for the Table object type to a   
//StringCollection object variable.   
StringCollection sc;   
sc = srv.GetDefaultInitFields(typ);   
//Set the default initialization fields for the Table object type to the CreateDate property.   
srv.SetDefaultInitFields(typ, "CreateDate");   
//Retrieve the Schema, Name, and CreateDate properties for every table in AdventureWorks2012.   
   //Note that the improvement in performance can be viewed in SQL Server Profiler.   
foreach ( tb in db.Tables) {   
   Console.WriteLine(tb.Schema + "." + tb.Name + " " + tb.CreateDate);   
}   
//Set the default initialization fields for the Table object type back to the original settings.   
srv.SetDefaultInitFields(typ, sc);   
}  
```  
  
  
