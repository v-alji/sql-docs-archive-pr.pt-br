---
title: Conexão do SQL Server para a criação de instância | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 81d0e7e2-d8f0-4bd9-9565-218ce996f28e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cdff17b763257c2a3280981c1f5c16040cc61413
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570816"
---
# <a name="sql-server-connection-for-instance-creation"></a><span data-ttu-id="a61e9-102">Conexão de SQL Server para a criação de instância</span><span class="sxs-lookup"><span data-stu-id="a61e9-102">SQL Server Connection for Instance Creation</span></span>
  <span data-ttu-id="a61e9-103">Uma das primeiras etapas ao criar uma Instância Oracle CDC é a criação de um banco de dados CDC na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="a61e9-103">One of the first steps when creating an Oracle CDC Instance is the creation of a CDC database on the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="a61e9-104">Este banco de dados CDC está habilitado para SQL Server CDC e esta habilitação exige um logon que é um membro da função de servidor fixa `sysadmin` .</span><span class="sxs-lookup"><span data-stu-id="a61e9-104">This CDC database is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="a61e9-105">Quando um usuário que inicia o assistente **Criar uma Instância Oracle CDC** não é membro da função de servidor fixa `sysadmin` , a caixa de diálogo **Conecte-se ao SQL Server** abre e pede as credenciais para um membro da função `sysadmin` para realizar a tarefa de habilitar o banco de dados para SQL Server CDC.</span><span class="sxs-lookup"><span data-stu-id="a61e9-105">When a user that starts the **Create an Oracle CDC Instance** wizard is not a member of the `sysadmin` fixed-server role, the **Connect to SQL Server** dialog box opens and requests the credentials for a member of the `sysadmin` role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="a61e9-106">Quando o banco de dados CDC é criado, o logon `sysadmin` é descartado e o trabalho é retomado com o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] original usado quando o Oracle Designer Console foi inserido.</span><span class="sxs-lookup"><span data-stu-id="a61e9-106">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="a61e9-107">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="a61e9-107">Task List</span></span>  
 <span data-ttu-id="a61e9-108">Insira as seguintes informações na caixa de diálogo **Conecte-se ao SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="a61e9-108">Enter the following information in the **Connect to SQL Server** dialog box.</span></span>  
  
 <span data-ttu-id="a61e9-109">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="a61e9-109">**Server Name**</span></span>  
 <span data-ttu-id="a61e9-110">Digite o nome do servidor em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está localizado.</span><span class="sxs-lookup"><span data-stu-id="a61e9-110">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
 <span data-ttu-id="a61e9-111">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="a61e9-111">**Authentication**</span></span>  
 <span data-ttu-id="a61e9-112">Selecione uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="a61e9-112">Select one of the following:</span></span>  
  
-   <span data-ttu-id="a61e9-113">**Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="a61e9-113">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="a61e9-114">**Autenticação do SQL Server**: se você selecionar esta opção, deverá digitar o **Logon** e a **Senha** para o usuário no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ao qual você está se conectando.</span><span class="sxs-lookup"><span data-stu-id="a61e9-114">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="a61e9-115">O logon deve ter uma função de banco de dados que permite acesso ao banco de dados MSXCDCDB.</span><span class="sxs-lookup"><span data-stu-id="a61e9-115">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="a61e9-116">É recomendado que o logon também tenha acesso a qualquer banco de dados adicional que está sendo usado ou o usuário não poderá exibir os dados nesses bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="a61e9-116">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
 <span data-ttu-id="a61e9-117">**Opções**</span><span class="sxs-lookup"><span data-stu-id="a61e9-117">**Options**</span></span>  
 <span data-ttu-id="a61e9-118">Clique na seta para exibir opções disponíveis a serem configuradas.</span><span class="sxs-lookup"><span data-stu-id="a61e9-118">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="a61e9-119">Você pode escolher deixar estas opções com o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="a61e9-119">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="a61e9-120">As opções disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="a61e9-120">The available options are:</span></span>  
  
-   <span data-ttu-id="a61e9-121">**Tempo limite da conexão**: Digite o tempo (em segundos) que o Serviço CDC para Oracle espera por uma conexão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de exceder o tempo limite. O valor padrão é **15**.</span><span class="sxs-lookup"><span data-stu-id="a61e9-121">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="a61e9-122">**Tempo limite de execução**: Digite o tempo (em segundos) que o Serviço do Windows do Oracle CDC espera que um comando seja executado antes de exceder o tempo limite. O valor padrão é **30**.</span><span class="sxs-lookup"><span data-stu-id="a61e9-122">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="a61e9-123">**Criptografar conexão**: selecione **Criptografar Conexão** para a comunicação entre o Serviço Oracle CDC e a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino usando uma conexão criptografada.</span><span class="sxs-lookup"><span data-stu-id="a61e9-123">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="a61e9-124">**Avançado**: Clique em **Avançado** e digite as propriedades de conexão adicionais na caixa de diálogo Propriedades Avançadas de Conexão, se necessário.</span><span class="sxs-lookup"><span data-stu-id="a61e9-124">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
     <span data-ttu-id="a61e9-125">Para obter informações sobre a caixa de diálogo Propriedades Avançadas de Conexão, consulte [Propriedades Avançadas de Conexão](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a61e9-125">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a61e9-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a61e9-126">See Also</span></span>  
 <span data-ttu-id="a61e9-127">[Criar o banco de dados de alteração do SQL Server](create-the-sql-server-change-database.md) </span><span class="sxs-lookup"><span data-stu-id="a61e9-127">[Create the SQL Server Change Database](create-the-sql-server-change-database.md) </span></span>  
 [<span data-ttu-id="a61e9-128">Permissões necessárias para conexão do SQL Server para o CDC Designer</span><span class="sxs-lookup"><span data-stu-id="a61e9-128">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
