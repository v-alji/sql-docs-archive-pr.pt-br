---
title: Permissões necessárias para conexão do SQL Server para o CDC Designer | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80334de2-17c1-43c9-951e-21a9f864e9cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0815a5d8f1cb66dee0d290a45166ebb395c8efa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569583"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-designer"></a><span data-ttu-id="a2e23-102">Permissões necessárias para conexão do SQL Server para o Designer CDC</span><span class="sxs-lookup"><span data-stu-id="a2e23-102">SQL Server Connection Required Permissions for the CDC Designer</span></span>
  <span data-ttu-id="a2e23-103">O CDC Designer Console exige informações de conexão para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executar suas tarefas.</span><span class="sxs-lookup"><span data-stu-id="a2e23-103">The CDC Designer Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform its tasks.</span></span> <span data-ttu-id="a2e23-104">Este tópico descreve as informações que podem ser fornecidas na caixa de diálogo **Conecte-se ao SQL Server** para definir a conexão para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2e23-104">This topic describes the information that can be provided in the **Connect to SQL Server** dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a2e23-105">A caixa de diálogo **Conecte-se ao SQL Server** abre quando necessário, como quando as informações de conexão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não estão disponíveis ou quando as informações existem, mas a conexão não tem as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="a2e23-105">The **Connect to SQL Server** dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="a2e23-106">A tabela a seguir descreve as várias tarefas em que uma conexão para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é necessária e as permissões necessárias de logon/usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a2e23-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="a2e23-107">Tarefa</span><span class="sxs-lookup"><span data-stu-id="a2e23-107">Task</span></span>|<span data-ttu-id="a2e23-108">Permissões mínimas</span><span class="sxs-lookup"><span data-stu-id="a2e23-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="a2e23-109">Exibir a lista de Serviços e Instâncias CDC usando a instância associada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a2e23-109">View the list of CDC Services and Instances using the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>|<span data-ttu-id="a2e23-110">`db_datareader` em MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="a2e23-110">`db_datareader` role on MSXDBCDC</span></span>|  
|<span data-ttu-id="a2e23-111">Iniciar/parar instâncias CDC</span><span class="sxs-lookup"><span data-stu-id="a2e23-111">Start/Stop CDC Instance(s)</span></span>|<span data-ttu-id="a2e23-112">`db_datareader` e `db_datawriter` no MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="a2e23-112">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="a2e23-113">Exibir o status da Instância CDC.</span><span class="sxs-lookup"><span data-stu-id="a2e23-113">View the CDC Instance status.</span></span>|<span data-ttu-id="a2e23-114">`db_owner` no banco de dados da Instância CDC</span><span class="sxs-lookup"><span data-stu-id="a2e23-114">`db_owner` role on the CDC Instance database</span></span>|  
|<span data-ttu-id="a2e23-115">Criar um novo banco de dados da Instância Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="a2e23-115">Create a new Oracle CDC Instance database.</span></span>|<span data-ttu-id="a2e23-116">`dbcreator` função de servidor fixa</span><span class="sxs-lookup"><span data-stu-id="a2e23-116">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="a2e23-117">Criar uma nova instância Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="a2e23-117">Create a new Oracle CDC Instance.</span></span>|<span data-ttu-id="a2e23-118">`db_datareader` em MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="a2e23-118">`db_datareader` role on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="a2e23-119">`db_owner` no banco de dados CDC que foi criado.</span><span class="sxs-lookup"><span data-stu-id="a2e23-119">`db_owner` role on the CDC database that was created.</span></span>|  
|<span data-ttu-id="a2e23-120">Obter scripts de implantação.</span><span class="sxs-lookup"><span data-stu-id="a2e23-120">Get deployment scripts.</span></span>|<span data-ttu-id="a2e23-121">`db_datareader` e `db_datawriter` no MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="a2e23-121">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="a2e23-122">`db_owner` no banco de dados CDC relacionado</span><span class="sxs-lookup"><span data-stu-id="a2e23-122">`db_owner` role on the relatedCDC database</span></span>|  
|<span data-ttu-id="a2e23-123">Alterar configuração e adicionar/remover instâncias de captura.</span><span class="sxs-lookup"><span data-stu-id="a2e23-123">Change configuration and add/remove capture instances.</span></span>|<span data-ttu-id="a2e23-124">`db_datareader` e `db_datawriter` no MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="a2e23-124">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="a2e23-125">`db_owner` no banco de dados CDC relacionado</span><span class="sxs-lookup"><span data-stu-id="a2e23-125">`db_owner` role on the related CDC database</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2e23-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2e23-126">See Also</span></span>  
 <span data-ttu-id="a2e23-127">[Acessar o CDC Designer Console](access-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="a2e23-127">[Access the CDC Designer Console](access-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="a2e23-128">Conexão do SQL Server para a criação de instância</span><span class="sxs-lookup"><span data-stu-id="a2e23-128">SQL Server Connection for Instance Creation</span></span>](sql-server-connection-for-instance-creation.md)  
  
  
