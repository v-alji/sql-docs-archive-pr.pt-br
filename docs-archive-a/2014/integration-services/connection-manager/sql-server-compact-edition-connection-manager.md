---
title: Gerenciador de Conexões do SQL Server Compact Edition | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Compact, connection manager
- connections [Integration Services], SQL Server Compact
- connection managers [Integration Services], SQL Server Compact
ms.assetid: ba627d4d-41f4-49fc-a921-f534cde67770
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d4feb001cc7c0fd0bd8b6e60d5ab22b33ad2eb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685239"
---
# <a name="sql-server-compact-edition-connection-manager"></a><span data-ttu-id="bc6c6-102">Gerenciador de Conexões do SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="bc6c6-102">SQL Server Compact Edition Connection Manager</span></span>
  <span data-ttu-id="bc6c6-103">Um gerenciador de conexões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact permite que um pacote se conecte a um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager enables a package to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span> <span data-ttu-id="bc6c6-104">O destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclui usa esse gerenciador de conexões para carregar dados em uma tabela no banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager to load data into a table in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc6c6-105">Em um computador de 64 bits, você deve executar pacotes que se conectam a fontes de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact no modo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-105">On a 64-bit computer, you must run packages that connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources in 32-bit mode.</span></span> <span data-ttu-id="bc6c6-106">O provedor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, que o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa para se conectar a fontes de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, só está disponível na versão de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact provider that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] uses to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources is available only in a 32-bit version.</span></span>  
  
## <a name="configuration-the-sql-server-compact-edition-connection-manager"></a><span data-ttu-id="bc6c6-107">Configuração do gerenciador de conexões do SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="bc6c6-107">Configuration the SQL Server Compact Edition Connection Manager</span></span>  
 <span data-ttu-id="bc6c6-108">Quando você adiciona um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Gerenciador de conexões compacta a um pacote, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] o cria um Gerenciador de conexões que será resolvido para uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conexão compacta em tempo de execução, define as propriedades do Gerenciador de conexões e adiciona o Gerenciador de conexões à `Connections` coleção no pacote.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-108">When you add a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="bc6c6-109">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `SQLMOBILE`.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-109">The `ConnectionManagerType` property of the connection manager is set to `SQLMOBILE`.</span></span>  
  
 <span data-ttu-id="bc6c6-110">Você pode configurar um gerenciador de conexões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="bc6c6-110">You can configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="bc6c6-111">Forneça uma cadeia de conexão que especifique o local do banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-111">Provide a connection string that specifies the location of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
-   <span data-ttu-id="bc6c6-112">Forneça uma senha para um banco de dados protegido por senha.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-112">Provide a password for a password-protected database.</span></span>  
  
-   <span data-ttu-id="bc6c6-113">Especifique o servidor no qual o banco de dados está armazenado.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-113">Specify the server on which the database is stored.</span></span>  
  
-   <span data-ttu-id="bc6c6-114">Indique se a conexão criada a partir do gerenciador de conexões será retida em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-114">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="bc6c6-115">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-115">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="bc6c6-116">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="bc6c6-116">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="bc6c6-117">Editor do Gerenciador de Conexões do SQL Server Compact Edition &#40;Página de Conexão&#41;</span><span class="sxs-lookup"><span data-stu-id="bc6c6-117">SQL Server Compact Edition Connection Manager Editor &#40;Connection Page&#41;</span></span>](../sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
-   [<span data-ttu-id="bc6c6-118">Editor do Gerenciador de Conexões do SQL Server Compact Edition &#40;Página Tudo&#41;</span><span class="sxs-lookup"><span data-stu-id="bc6c6-118">SQL Server Compact Edition Connection Manager Editor &#40;All Page&#41;</span></span>](../sql-server-compact-edition-connection-manager-editor-all-page.md)  
  
 <span data-ttu-id="bc6c6-119">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="bc6c6-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
