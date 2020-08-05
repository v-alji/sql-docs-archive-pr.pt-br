---
title: Permissões necessárias para conexão do SQL Server para o Serviço CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9e968f9-180c-4fa0-a849-98f2b1942330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e63b98ffd0371bd5b70ecc0ac843ad40a4a5d03e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572639"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-service"></a><span data-ttu-id="7a4b3-102">Permissões necessárias para conexão do SQL Server para o Serviço CDC</span><span class="sxs-lookup"><span data-stu-id="7a4b3-102">SQL Server Connection Required Permissions for the CDC Service</span></span>
  <span data-ttu-id="7a4b3-103">O Console de Configuração do Serviço CDC exige informações de conexão para que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] execute suas tarefas.</span><span class="sxs-lookup"><span data-stu-id="7a4b3-103">The CDC Service Configuration Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform their tasks.</span></span> <span data-ttu-id="7a4b3-104">Este tópico descreve as informações que podem ser fornecidas na caixa de diálogo Conecte-se ao SQL Server para definir a conexão para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a4b3-104">This topic describes the information that can be provided in the Connect to SQL Server dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7a4b3-105">A caixa de diálogo Conecte-se ao SQL Server abre quando necessário, como quando as informações de conexão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não estão disponíveis ou quando as informações existem, mas a conexão não tem as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="7a4b3-105">The Connect to SQL Server dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="7a4b3-106">A tabela a seguir descreve as várias tarefas em que uma conexão para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é necessária e as permissões necessárias de logon/usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a4b3-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="7a4b3-107">Tarefa</span><span class="sxs-lookup"><span data-stu-id="7a4b3-107">Task</span></span>|<span data-ttu-id="7a4b3-108">Permissões mínimas</span><span class="sxs-lookup"><span data-stu-id="7a4b3-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="7a4b3-109">Preparar a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a4b3-109">Prepare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance.</span></span>|<span data-ttu-id="7a4b3-110">`dbcreator` função de servidor fixa</span><span class="sxs-lookup"><span data-stu-id="7a4b3-110">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="7a4b3-111">Crie um logon Oracle CDC Service-SQL Server para ser usado pelo serviço Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="7a4b3-111">Create an Oracle CDC Service-SQL Server login for use by the Oracle CDC service.</span></span>|<span data-ttu-id="7a4b3-112">`public` função de servidor fixa</span><span class="sxs-lookup"><span data-stu-id="7a4b3-112">`public` fixed-server role</span></span>|  
|<span data-ttu-id="7a4b3-113">Crie um logon do Serviço Oracle CDC para usar para registrar o novo serviço no MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="7a4b3-113">Create an Oracle CDC Service-login to use for registering the new service in MSXDBCDC.</span></span>|<span data-ttu-id="7a4b3-114">`db_datareader` e `db_datawriter` no MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="7a4b3-114">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="7a4b3-115">Editar um logon do Serviço Oracle CDC para atualizar o registro do serviço no MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="7a4b3-115">Edit an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="7a4b3-116">`db_datareader` e `db_datawriter` no MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="7a4b3-116">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="7a4b3-117">Excluir um logon do Serviço Oracle CDC para atualizar o registro do serviço no MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="7a4b3-117">Delete an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="7a4b3-118">`db_datareader` e `db_datawriter` no MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="7a4b3-118">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a4b3-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7a4b3-119">See Also</span></span>  
 <span data-ttu-id="7a4b3-120">[Conexão com o SQL Server](connection-to-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a4b3-120">[Connection to SQL Server](connection-to-sql-server.md) </span></span>  
 [<span data-ttu-id="7a4b3-121">Conexão com o SQL Server para exclusão</span><span class="sxs-lookup"><span data-stu-id="7a4b3-121">Connection to SQL Server for Delete</span></span>](connection-to-sql-server-for-delete.md)  
  
  
