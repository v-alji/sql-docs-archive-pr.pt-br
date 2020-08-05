---
title: Representação do banco de dados (tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 16a233fb-f83b-4ca1-acb5-6186eca0a62c
author: minewiskan
ms.author: owend
ms.openlocfilehash: c327e07685e98e6fa9f992025510e869d909e5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572233"
---
# <a name="database-representationtabular"></a><span data-ttu-id="ae072-102">Representação de banco de dados (de tabela)</span><span class="sxs-lookup"><span data-stu-id="ae072-102">Database Representation(Tabular)</span></span>
  <span data-ttu-id="ae072-103">No Modo de Tabela, o banco de dados é o contêiner de todos os objetos no modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="ae072-103">In Tabular Mode, the database is the container for all objects in the tabular model.</span></span>  
  
## <a name="database-representation"></a><span data-ttu-id="ae072-104">Representação de banco de dados</span><span class="sxs-lookup"><span data-stu-id="ae072-104">Database Representation</span></span>  
 <span data-ttu-id="ae072-105">O banco de dados é o local onde residem todos os objetos que constituem um modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="ae072-105">The database is the place where all objects that form a tabular model reside.</span></span> <span data-ttu-id="ae072-106">O desenvolvedor localiza no banco de dados objetos como conexões, tabelas, funções e muito mais.</span><span class="sxs-lookup"><span data-stu-id="ae072-106">Contained by the database, the developer finds objects like connections, tables, roles and many more.</span></span>  
  
### <a name="database-in-amo"></a><span data-ttu-id="ae072-107">Banco de dados no AMO</span><span class="sxs-lookup"><span data-stu-id="ae072-107">Database in AMO</span></span>  
 <span data-ttu-id="ae072-108">Ao usar o AMO para gerenciar um banco de dados modelo de tabela, o objeto <xref:Microsoft.AnalysisServices.Database> no AMO coincide um-para-um ao objeto lógico de banco de dados em um modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="ae072-108">When using AMO to manage a tabular model database, the <xref:Microsoft.AnalysisServices.Database> object in AMO matches one-to-one the database logical object in a tabular model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae072-109">Para obter acesso a um objeto de banco de dados, no AMO, o usuário precisa ter acesso a um objeto de servidor e conectar-se a ele.</span><span class="sxs-lookup"><span data-stu-id="ae072-109">In order to gain access to a database object, in AMO, the user needs to have access to a server object and connect to it.</span></span>  
  
### <a name="database-in-adomdnet"></a><span data-ttu-id="ae072-110">Banco de dados no ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="ae072-110">Database in ADOMD.Net</span></span>  
 <span data-ttu-id="ae072-111">Ao usar o ADOMD para consultar um banco de dados modelo de tabela, a conexão com um banco de dados específico é obtida por meio do objeto <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>.</span><span class="sxs-lookup"><span data-stu-id="ae072-111">When using ADOMD to consult and query a tabular model database, connection to a specific database is obtained through the <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> object.</span></span>  
  
 <span data-ttu-id="ae072-112">Você pode se conectar diretamente a determinado banco de dados usando o seguinte snippet de código:</span><span class="sxs-lookup"><span data-stu-id="ae072-112">You can connect directly to a certain database using the following code snippet:</span></span>  
  
```csharp  
using ADOMD = Microsoft.AnalysisServices.AdomdClient;  
...  
   ADOMD.AdomdConnection currrentCnx = new ADOMD.AdomdConnection("Data Source=<<server\instance>>;Catalog=<<database>>");  
   currrentCnx.Open();  
...  
  
```  
  
 <span data-ttu-id="ae072-113">Além disso, em um objeto de conexão existente (que não foi fechado), você pode alterar o banco de dados atual para outro, conforme mostrado no seguinte snippet de código:</span><span class="sxs-lookup"><span data-stu-id="ae072-113">Also, over an existing connection object (that hasn't been closed), you can change the current database to another as shown in the following code snippet:</span></span>  
  
```csharp  
currentCnx.ChangeDatabase("myOtherDatabase");  
  
```  
  
## <a name="database-in-amo"></a><span data-ttu-id="ae072-114">Banco de dados no AMO</span><span class="sxs-lookup"><span data-stu-id="ae072-114">Database in AMO</span></span>  
 <span data-ttu-id="ae072-115">Ao usar o AMO para gerenciar um objeto de banco de dados, comece com um objeto <xref:Microsoft.AnalysisServices.Server>.</span><span class="sxs-lookup"><span data-stu-id="ae072-115">When using AMO to manage a database object, start with a <xref:Microsoft.AnalysisServices.Server> object.</span></span> <span data-ttu-id="ae072-116">Em seguida, procure seu banco de dados na coleção de banco de dados ou crie um novo banco de dados adicionando um à coleção.</span><span class="sxs-lookup"><span data-stu-id="ae072-116">Then search for your database in the databases collection or create a new database by adding one to the collection.</span></span>  
  
 <span data-ttu-id="ae072-117">O trecho de código a seguir mostra as etapas para se conectar a um servidor e criar um banco de dados vazio, depois de verificar se o banco de dados não existe:</span><span class="sxs-lookup"><span data-stu-id="ae072-117">The following code snippet shows the steps to connect to a server and create an empty database, after checking the database doesn't exist:</span></span>  
  
```  
  
AMO.Server CurrentServer = new AMO.Server();  
try  
{  
    CurrentServer.Connect(currentServerName);  
}  
catch (Exception cnxException)  
{  
    MessageBox.Show(string.Format("Error while trying to connect to server: [{0}]\nError message: {1}", currentServerName, cnxException.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    return;  
}  
newDatabaseName = DatabaseName.Text;  
if (CurrentServer.Databases.Contains(newDatabaseName))  
{  
    return;  
}  
try  
{  
    AMO.Database newDatabase = CurrentServer.Databases.Add(newDatabaseName);  
  
    CurrentServer.Update();  
}  
catch (Exception createDBxc)  
{  
    MessageBox.Show(String.Format("Database [{0}] couldn't be created.\n{1}", newDatabaseName, createDBxc.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    newDatabaseAvailable = false;  
}  
  
```  
  
 <span data-ttu-id="ae072-118">Para obter um entendimento prático de como usar o AMO para criar e manipular representações de banco de dados, consulte o código-fonte do exemplo Tabular AMO 2012; verifique especificamente o seguinte arquivo de origem: Database.cs.</span><span class="sxs-lookup"><span data-stu-id="ae072-118">For a practical understanding on how to use AMO to create and manipulate database representations, see source code in the Tabular AMO 2012 sample; specifically check in the following source file: Database.cs.</span></span> <span data-ttu-id="ae072-119">O código de exemplo é fornecido apenas como um suporte aos conceitos lógicos explicados aqui e não deve ser usado em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="ae072-119">Sample code is provided only as a support to the logical concepts explained here, and should not be used in a production environment.</span></span>  
  
  
