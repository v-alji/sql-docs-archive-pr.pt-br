---
title: Acessar o CDC Designer Console | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- accMsDes
ms.assetid: b168c64e-c1b5-42d4-a92a-84de1dd0324e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4f6e4df0a514cb29e36bcd1270b2537dc3ba68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685246"
---
# <a name="access-the-cdc-designer-console"></a><span data-ttu-id="05432-102">Acessar o CDC Designer Console</span><span class="sxs-lookup"><span data-stu-id="05432-102">Access the CDC Designer Console</span></span>
  <span data-ttu-id="05432-103">Você pode acessar o CDC Designer Console do computador onde instalou o console.</span><span class="sxs-lookup"><span data-stu-id="05432-103">You can access the CDC Designer Console from the computer where you installed the console.</span></span> <span data-ttu-id="05432-104">Para obter mais informações sobre a instalação, consulte Instalação.</span><span class="sxs-lookup"><span data-stu-id="05432-104">For more information about installation, see Installation.</span></span>  
  
 <span data-ttu-id="05432-105">Quando você abre o CDC Designer Console, a caixa de diálogo Conecte-se ao SQL Server é aberta.</span><span class="sxs-lookup"><span data-stu-id="05432-105">When you open the CDC Designer Console, the Connect to SQL Server dialog box opens.</span></span>  
  
 <span data-ttu-id="05432-106">O logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que acessa o CDC Designer deve ter permissões UPDATE no banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="05432-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that accesses the CDC Designer must have UPDATE permissions on the MSXDBCDC database.</span></span> <span data-ttu-id="05432-107">Além disso, o logon também tem que ter a função de servidor fixa `dbcreator` para criar novas Instâncias Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="05432-107">In addition, the login must also have the `dbcreator` fixed-server role to create new Oracle CDC Instances.</span></span> <span data-ttu-id="05432-108">É recomendado que o logon também tenha acesso SELECT aos bancos de dados CDC que estão sendo usados ou o usuário não poderá exibir o estado desses bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="05432-108">It is recommended that the login also have SELECT access to the CDC databases being used or the user will not be able to view the state of those databases.</span></span>  
  
 <span data-ttu-id="05432-109">Insira as seguintes informações na caixa de diálogo Conecte-se ao SQL Server.</span><span class="sxs-lookup"><span data-stu-id="05432-109">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="05432-110">Nome do servidor</span><span class="sxs-lookup"><span data-stu-id="05432-110">Server Name</span></span>  
 <span data-ttu-id="05432-111">Digite o nome do servidor em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está localizado.</span><span class="sxs-lookup"><span data-stu-id="05432-111">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="05432-112">Autenticação</span><span class="sxs-lookup"><span data-stu-id="05432-112">Authentication</span></span>  
 <span data-ttu-id="05432-113">Selecione uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="05432-113">Select one of the following:</span></span>  
  
-   <span data-ttu-id="05432-114">**Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="05432-114">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="05432-115">**Autenticação do SQL Server**: se você selecionar esta opção, deverá digitar o **Logon** e a **Senha** para o usuário no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ao qual você está se conectando.</span><span class="sxs-lookup"><span data-stu-id="05432-115">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="05432-116">O logon deve ter uma função de banco de dados que permite acesso ao banco de dados MSXCDCDB.</span><span class="sxs-lookup"><span data-stu-id="05432-116">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="05432-117">É recomendado que o logon também tenha acesso a qualquer banco de dados adicional que está sendo usado ou o usuário não poderá exibir os dados nesses bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="05432-117">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
### <a name="options"></a><span data-ttu-id="05432-118">Opções</span><span class="sxs-lookup"><span data-stu-id="05432-118">Options</span></span>  
 <span data-ttu-id="05432-119">Clique na seta para exibir opções disponíveis a serem configuradas.</span><span class="sxs-lookup"><span data-stu-id="05432-119">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="05432-120">Você pode escolher deixar estas opções com o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="05432-120">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="05432-121">As opções disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="05432-121">The available options are:</span></span>  
  
 <span data-ttu-id="05432-122">**Tempo-limite da conexão**</span><span class="sxs-lookup"><span data-stu-id="05432-122">**Connection Timeout**</span></span>  
 <span data-ttu-id="05432-123">Digite o tempo (em segundos) que o Serviço CDC para Oracle espera por uma conexão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de exceder o tempo limite. O valor padrão é **15**.</span><span class="sxs-lookup"><span data-stu-id="05432-123">Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
 <span data-ttu-id="05432-124">**Tempo Limite de Execução**</span><span class="sxs-lookup"><span data-stu-id="05432-124">**Execution Timeout**</span></span>  
 <span data-ttu-id="05432-125">Digite o tempo (em segundos) que o Serviço do Windows do Oracle CDC espera que um comando seja executado antes de exceder o tempo limite. O valor padrão é **30**.</span><span class="sxs-lookup"><span data-stu-id="05432-125">Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
 <span data-ttu-id="05432-126">**Criptografar conexão**</span><span class="sxs-lookup"><span data-stu-id="05432-126">**Encrypt Connection**</span></span>  
 <span data-ttu-id="05432-127">Selecione **Criptografar Conexão** para a comunicação entre o Serviço Oracle CDC e a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino usando uma conexão criptografada.**Avançado**: Clique em **Avançado** e digite as propriedades de conexão adicionais na caixa de diálogo Propriedades Avançadas de Conexão, se necessário.</span><span class="sxs-lookup"><span data-stu-id="05432-127">Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="05432-128">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="05432-128">**Advanced**</span></span>  
 <span data-ttu-id="05432-129">Clique em **Avançado** e digite as propriedades de conexão adicionais na caixa de diálogo Propriedades Avançadas de Conexão, se necessário.</span><span class="sxs-lookup"><span data-stu-id="05432-129">Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="05432-130">Para obter informações sobre a caixa de diálogo Propriedades Avançadas de Conexão, consulte [Propriedades Avançadas de Conexão](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="05432-130">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05432-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05432-131">See Also</span></span>  
 [<span data-ttu-id="05432-132">Permissões necessárias para conexão do SQL Server para o CDC Designer</span><span class="sxs-lookup"><span data-stu-id="05432-132">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
