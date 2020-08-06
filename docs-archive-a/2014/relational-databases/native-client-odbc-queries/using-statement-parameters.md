---
title: Usando parâmetros de instrução | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- ODBC, parameters
- statements [ODBC], parameters
- parameter markers [ODBC]
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
ms.assetid: 2427d886-ec6c-49d7-b0b6-0d998b64cdb9
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b7e207416e60af94efd59555980a0edff68a38b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569401"
---
# <a name="using-statement-parameters"></a><span data-ttu-id="d3ac0-102">Usando parâmetros de instrução</span><span class="sxs-lookup"><span data-stu-id="d3ac0-102">Using Statement Parameters</span></span>
  <span data-ttu-id="d3ac0-103">Um parâmetro é uma variável em uma instrução SQL que pode permitir a aplicativo ODBC:</span><span class="sxs-lookup"><span data-stu-id="d3ac0-103">A parameter is a variable in an SQL statement that can enable an ODBC application to:</span></span>  
  
-   <span data-ttu-id="d3ac0-104">Fornecer valores com eficiência para colunas em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-104">Efficiently provide values for columns in a table.</span></span>  
  
-   <span data-ttu-id="d3ac0-105">Aprimorar a interação do usuário na construção dos critérios de consulta.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-105">Enhance user interaction in constructing query criteria.</span></span>  
  
-   <span data-ttu-id="d3ac0-106">Gerencie dados de **texto**, **ntext**e **imagem** e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados C específicos.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-106">Manage **text**, **ntext**, and **image** data and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific C data types.</span></span>  
  
 <span data-ttu-id="d3ac0-107">Por exemplo, uma tabela de **peças** tem colunas denominadas **partid**, **Descrição**e **preço**.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-107">For example, a **Parts** table has columns named **PartID**, **Description**, and **Price**.</span></span> <span data-ttu-id="d3ac0-108">Adicionar uma parte sem parâmetros exige a criação de uma instrução SQL como, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d3ac0-108">To add a part without parameters requires constructing an SQL statement such as:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (2100, 'Drive shaft', 50.00)  
```  
  
 <span data-ttu-id="d3ac0-109">Embora essa instrução seja aceitável para inserir uma linha com um conjunto conhecido de valores, é estranho quando um aplicativo precisa inserir várias linhas.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-109">Although this statement is acceptable for inserting one row with a known set of values, it is awkward when an application is required to insert several rows.</span></span> <span data-ttu-id="d3ac0-110">O ODBC resolve isso permitindo que um aplicativo substitua um valor de dados em uma instrução SQL por um marcador de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-110">ODBC addresses this by letting an application to replace any data value in an SQL statement by a parameter maker.</span></span> <span data-ttu-id="d3ac0-111">Isto é indicado por um ponto de interrogação (?).</span><span class="sxs-lookup"><span data-stu-id="d3ac0-111">This is denoted by a question mark (?).</span></span> <span data-ttu-id="d3ac0-112">No seguinte exemplo, três valores de dados com marcadores de parâmetro são substituídos:</span><span class="sxs-lookup"><span data-stu-id="d3ac0-112">In the following example, three data values are replaced with parameter markers:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="d3ac0-113">Os marcadores de parâmetro são associados a variáveis do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-113">The parameter markers are then bound to application variables.</span></span> <span data-ttu-id="d3ac0-114">Para inserir uma nova linha, o aplicativo só precisa definir os valores das variáveis e executar a instrução.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-114">To insert a new row, the application has only to set the values of the variables and execute the statement.</span></span> <span data-ttu-id="d3ac0-115">O driver recupera os valores atuais das variáveis e os envia para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-115">The driver then retrieves the current values of the variables and sends them to the data source.</span></span> <span data-ttu-id="d3ac0-116">Caso a instrução seja executada várias vezes, o aplicativo pode tornar o processo até mesmo mais eficiente, preparando a instrução.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-116">If the statement is executed multiple times, the application can make the process even more efficient by preparing the statement.</span></span>  
  
 <span data-ttu-id="d3ac0-117">Cada marcador de parâmetro é referenciado por seu número ordinal atribuído aos parâmetros da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-117">Each parameter marker is referenced by its ordinal number assigned to the parameters from left to right.</span></span> <span data-ttu-id="d3ac0-118">O marcador de parâmetro à esquerda em uma instrução SQL tem um valor ordinal igual a 1; o próximo é ordinal 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d3ac0-118">The leftmost parameter marker in an SQL statement has an ordinal value of 1; the next one is ordinal 2, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3ac0-119">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d3ac0-119">In This Section</span></span>  
  
-   [<span data-ttu-id="d3ac0-120">Associando parâmetros</span><span class="sxs-lookup"><span data-stu-id="d3ac0-120">Binding Parameters</span></span>](using-statement-parameters-binding-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="d3ac0-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d3ac0-121">See Also</span></span>  
 [<span data-ttu-id="d3ac0-122">Executando consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="d3ac0-122">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
