---
title: Conexão ao SQL Server para exclusão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 030b10c2-6b88-4c2c-bf67-22994be25a60
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f5f069f7686e8b6fa9176f92c9e2f47be5f2c71a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570820"
---
# <a name="connection-to-sql-server-for-delete"></a><span data-ttu-id="8d80e-102">Conexão para o SQL Server para exclusão</span><span class="sxs-lookup"><span data-stu-id="8d80e-102">Connection to SQL Server for Delete</span></span>
  <span data-ttu-id="8d80e-103">Quando um logon sem uma função de banco de dados que inclui permissão de gravação (por exemplo a função **db_owner** ) ao banco de dados MSXDBCDC tenta excluir uma instância Oracle CDC, a caixa de diálogo Conectar-se ao SQL Server é exibida.</span><span class="sxs-lookup"><span data-stu-id="8d80e-103">When a login without a database role that includes write permission (for example the **db_owner** role) to the MSXDBCDC database attempts to delete an Oracle CDC instance, the Connect to SQL Server dialog box is displayed.</span></span>  
  
 <span data-ttu-id="8d80e-104">Nesta caixa de diálogo, você deve inserir as credenciais de um logon que tem permissão de gravação ao banco de dados MSXDBCDC, como a função de banco de dados **db_owner** para excluir a instância Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="8d80e-104">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role to delete the Oracle CDC instance.</span></span>  
  
 <span data-ttu-id="8d80e-105">Insira as seguintes informações na caixa de diálogo Conecte-se ao SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8d80e-105">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
 <span data-ttu-id="8d80e-106">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="8d80e-106">**Server Name**</span></span>  
 <span data-ttu-id="8d80e-107">Digite o nome do servidor em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está localizado.</span><span class="sxs-lookup"><span data-stu-id="8d80e-107">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
 <span data-ttu-id="8d80e-108">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="8d80e-108">**Authentication**</span></span>  
 <span data-ttu-id="8d80e-109">Selecione uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="8d80e-109">Select one of the following:</span></span>  
  
-   <span data-ttu-id="8d80e-110">**Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="8d80e-110">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="8d80e-111">**Autenticação do SQL Server**: se você selecionar esta opção, deverá digitar o **Logon** e **Senha** para o usuário no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ao qual você está se conectando.</span><span class="sxs-lookup"><span data-stu-id="8d80e-111">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="8d80e-112">**Opções**</span><span class="sxs-lookup"><span data-stu-id="8d80e-112">**Options**</span></span>  
 <span data-ttu-id="8d80e-113">Clique na seta para exibir opções disponíveis a serem configuradas.</span><span class="sxs-lookup"><span data-stu-id="8d80e-113">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="8d80e-114">Você pode escolher deixar estas opções com o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="8d80e-114">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="8d80e-115">As opções disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="8d80e-115">The available options are:</span></span>  
  
-   <span data-ttu-id="8d80e-116">**Tempo Limite de Conexão**: digite o tempo (em segundos) que o programa aguarda até que uma conexão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] seja estabelecida antes de gerar um erro de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="8d80e-116">**Connection Timeout**: Type the time (in seconds) the program waits for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection to be established before producing a timeout error.</span></span> <span data-ttu-id="8d80e-117">O valor padrão é **15**.</span><span class="sxs-lookup"><span data-stu-id="8d80e-117">The default value is **15**.</span></span>  
  
-   <span data-ttu-id="8d80e-118">**Tempo Limite de Execução**: digite o tempo (em segundos) que o programa aguarda até que uma execução de comando do SQL seja concluída antes de gerar um erro de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="8d80e-118">**Execution Timeout**: Type the time (in seconds) that the program waits for SQL command execution to finish before producing a timeout error.</span></span> <span data-ttu-id="8d80e-119">O valor padrão é **30**.</span><span class="sxs-lookup"><span data-stu-id="8d80e-119">The default value is **30**.</span></span>  
  
-   <span data-ttu-id="8d80e-120">**Criptografar Conexão**: selecione **Criptografar Conexão** para verificar se a conexão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo estabelecida está criptografada para garantir a privacidade.</span><span class="sxs-lookup"><span data-stu-id="8d80e-120">**Encrypt Connection**: Select **Encrypt Connection** to ensure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection that being established is encrypted to guarantee privacy.</span></span>  
  
-   <span data-ttu-id="8d80e-121">**Avançado**: clique em **Avançado** e digite as propriedades de conexão adicionais na caixa de diálogo Propriedades Avançadas da Conexão, se necessário.</span><span class="sxs-lookup"><span data-stu-id="8d80e-121">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d80e-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8d80e-122">See Also</span></span>  
 [<span data-ttu-id="8d80e-123">Permissões necessárias para conexão do SQL Server para o Serviço CDC</span><span class="sxs-lookup"><span data-stu-id="8d80e-123">SQL Server Connection Required Permissions for the CDC Service</span></span>](sql-server-connection-required-permissions-for-the-cdc-service.md)  
  
  
