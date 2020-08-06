---
title: Criar o banco de dados de alteração do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraIns
ms.assetid: 4f79c24a-e99a-4a06-8637-51eeec406259
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaeb26d5bea4c9e50db29aaa45297ba763dbbfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684826"
---
# <a name="create-the-sql-server-change-database"></a><span data-ttu-id="ae29e-102">Criar o banco de dados de alteração do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae29e-102">Create the SQL Server Change Database</span></span>
  <span data-ttu-id="ae29e-103">Quando você inicia o assistente Nova Instância, a página Criar Banco de Dados CDC é aberta.</span><span class="sxs-lookup"><span data-stu-id="ae29e-103">When you start the New Instance wizard, the Create CDC Database page opens.</span></span> <span data-ttu-id="ae29e-104">Use a página Criar Banco de Dados CDC para fornecer informações sobre a nova instância CDC e criar um novo banco de dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="ae29e-104">Use the Create CDC Database page to provide information about the new CDC instance and create a new Change database.</span></span>  
  
 <span data-ttu-id="ae29e-105">Quando você cria um novo banco de dados CDC, ele está habilitado para SQL Server CDC e esta habilitação exige um logon que é um membro da função de servidor fixa `sysadmin` .</span><span class="sxs-lookup"><span data-stu-id="ae29e-105">When you create a new CDC database it is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="ae29e-106">Quando um usuário que inicia o assistente Criar uma Instância Oracle CDC não é membro da função de servidor fixa `sysadmin` , a caixa de diálogo Conecte-se ao SQL Server abre e pede as credenciais para um membro da função sysadmin para realizar a tarefa de habilitar o banco de dados para SQL Server CDC.</span><span class="sxs-lookup"><span data-stu-id="ae29e-106">When a user that starts the Create an Oracle CDC Instance wizard is not a member of the `sysadmin` fixed-server role, the Connect to SQL Server dialog box opens and requests the credentials for a member of the sysadmin role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="ae29e-107">Quando o banco de dados CDC é criado, o logon `sysadmin` é descartado e o trabalho é retomado com o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] original usado quando o Oracle Designer Console foi inserido.</span><span class="sxs-lookup"><span data-stu-id="ae29e-107">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ae29e-108">Para tarefas diferentes de Habilitar o banco de dados para SQL Server CDC de, o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usado para executar o Assistente de Nova Instância deverá ter a função de servidor fixa `dbcreator` e permissões UPDATE no banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="ae29e-108">For tasks other than Enable the database for SQL Server CDC of, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used for running the New Instance Wizard must have the `dbcreator` fixed-server role and UPDATE permissions on the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="ae29e-109">Para obter informações sobre como inserir os dados na caixa de diálogo Conecte-se ao SQL Server, consulte [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span><span class="sxs-lookup"><span data-stu-id="ae29e-109">For information on entering the data in the Connect to SQL Server dialog box, see [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae29e-110">Opções</span><span class="sxs-lookup"><span data-stu-id="ae29e-110">Options</span></span>  
 <span data-ttu-id="ae29e-111">**Instância Oracle CDC**</span><span class="sxs-lookup"><span data-stu-id="ae29e-111">**Oracle CDC Instance**</span></span>  
 <span data-ttu-id="ae29e-112">Digite as seguintes informações sobre a instância CDC que você está criando.</span><span class="sxs-lookup"><span data-stu-id="ae29e-112">Type the following information about the CDC instance you are creating.</span></span>  
  
-   <span data-ttu-id="ae29e-113">**Nome**: digite um nome para o novo serviço.</span><span class="sxs-lookup"><span data-stu-id="ae29e-113">**Name**: Type a name for the new service.</span></span> <span data-ttu-id="ae29e-114">Este também será o nome do novo banco de dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="ae29e-114">This will also be the name of the new Change database.</span></span>  
  
-   <span data-ttu-id="ae29e-115">**Descrição**: digite uma descrição para a nova instância para ajudar a identificá-la.</span><span class="sxs-lookup"><span data-stu-id="ae29e-115">**Description**: Type a description for the new instance to help you identify it.</span></span> <span data-ttu-id="ae29e-116">Isso é opcional.</span><span class="sxs-lookup"><span data-stu-id="ae29e-116">This is optional.</span></span>  
  
 <span data-ttu-id="ae29e-117">**Banco de Dados de alteração do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ae29e-117">**SQL Server Change Database**</span></span>  
 <span data-ttu-id="ae29e-118">Esta seção é usada para criar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ae29e-118">This section is used to create the database.</span></span>  
  
1.  <span data-ttu-id="ae29e-119">**Banco de Dados de Alteração**: o nome do novo banco de dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="ae29e-119">**Change Database**: The name of the new Change database.</span></span> <span data-ttu-id="ae29e-120">O nome do banco de dados é o mesmo que o nome que você deu à instância.</span><span class="sxs-lookup"><span data-stu-id="ae29e-120">The name of the database is the same as the name that you gave to the instance.</span></span> <span data-ttu-id="ae29e-121">Este campo somente leitura exibe o caminho completo para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ae29e-121">This read-only field displays the full path to the database.</span></span>  
  
2.  <span data-ttu-id="ae29e-122">**Criar Banco de Dados**: clique em **Criar Banco de Dados** para criar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ae29e-122">**Create Database**: Click **Create Database** to create the database.</span></span>  
  
     <span data-ttu-id="ae29e-123">Para criar o banco de dados, o logon deve ter a função de servidor `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="ae29e-123">To create the database, the login must have the `sysasmin` server role.</span></span> <span data-ttu-id="ae29e-124">Consulte a observação de segurança acima para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ae29e-124">See the security note above for more information.</span></span>  
  
     <span data-ttu-id="ae29e-125">Depois que você criar o banco de dados, clique em **Avançar** para [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md).</span><span class="sxs-lookup"><span data-stu-id="ae29e-125">After you create the database, you can click **Next** to [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae29e-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ae29e-126">See Also</span></span>  
 <span data-ttu-id="ae29e-127">[Como criar a instância de banco de dados de alteração do SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="ae29e-127">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="ae29e-128">O Serviço Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="ae29e-128">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
  
