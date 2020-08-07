---
title: Conectando-se a um banco de dados SQL do Azure usando SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 0dc20bb6-b142-4259-b87b-427d2ba798af
author: rothja
ms.author: jroth
ms.openlocfilehash: 177c655f97e32f2044460e87c6cd775cdf8fcde9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575079"
---
# <a name="connecting-to-an-azure-sql-database-using-sql-server-native-client"></a><span data-ttu-id="9b43e-102">Connecting to an Azure SQL Database Using SQL Server Native Client (Conectando a um Banco de Dados SQL do Azure usando o SQL Server Native Client)</span><span class="sxs-lookup"><span data-stu-id="9b43e-102">Connecting to an Azure SQL Database Using SQL Server Native Client</span></span>
  <span data-ttu-id="9b43e-103">Para obter um exemplo que mostra como se conectar a um [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)] usando um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cliente nativo, consulte [desenvolvimento: tópicos de instruções (banco de dados SQL do Azure)](https://msdn.microsoft.com/library/ee621787.aspx).</span><span class="sxs-lookup"><span data-stu-id="9b43e-103">For a sample that shows how to connect to a [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, see [Development: How-to Topics (Azure SQL Database)](https://msdn.microsoft.com/library/ee621787.aspx).</span></span>  
  
## <a name="known-issues-when-connecting-to-a-sql-database"></a><span data-ttu-id="9b43e-104">Problemas conhecidos ao conectar a um banco de dados SQL</span><span class="sxs-lookup"><span data-stu-id="9b43e-104">Known Issues When Connecting to a SQL Database</span></span>  
 <span data-ttu-id="9b43e-105">Estes são problemas conhecidos ao conectar a um [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] usando o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span><span class="sxs-lookup"><span data-stu-id="9b43e-105">The following are known issues when connecting to a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span></span>  
  
-   <span data-ttu-id="9b43e-106">Uma conexão feita com o `SQLBrowseConnect` poderá ser rejeitada se `SQLBrowseConnect` for usado em fases.</span><span class="sxs-lookup"><span data-stu-id="9b43e-106">A connection made with `SQLBrowseConnect` may be rejected if `SQLBrowseConnect` is used in stages.</span></span>  <span data-ttu-id="9b43e-107">Por exemplo, se o nome do driver for enviado na primeira chamada, o servidor e as credenciais (usuário e senha) serão enviados na segunda chamada, estabelecendo a conexão, e um nome de banco de dados e um idioma na terceira chamada.</span><span class="sxs-lookup"><span data-stu-id="9b43e-107">For example, if the driver name is sent in the first call, server and credentials (user and password) sent in the second call, establishing the connection, and a database name and a language in the third call.</span></span>  <span data-ttu-id="9b43e-108">A terceira chamada levará o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client a emitir uma instrução USE para alterar bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="9b43e-108">The third call will cause [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to issue a USE statement to change databases.</span></span> <span data-ttu-id="9b43e-109">Entretanto, a instrução USE não tem suporte no [!INCLUDE[ssSDS](../../../includes/sssds-md.md)], gerando o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="9b43e-109">However, the USE statement is not supported in [!INCLUDE[ssSDS](../../../includes/sssds-md.md)], generating the following error:</span></span>  
  
    ```  
    [Microsoft][SQL Server Native Client 11.0][SQL Server]USE statement is not supported to switch between databases. Use a new connection to connect to a different Database.  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9b43e-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b43e-110">See Also</span></span>  
 [<span data-ttu-id="9b43e-111">Criando aplicativos com o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="9b43e-111">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
