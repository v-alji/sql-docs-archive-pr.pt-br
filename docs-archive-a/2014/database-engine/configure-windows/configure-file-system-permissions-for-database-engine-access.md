---
title: Configurar permissões do sistema de arquivos para acesso ao Mecanismo de Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- file system permissions
- service account [SQL Server], file system permissions
- permissions [SQL Server], file system
ms.assetid: 78bba43c-4edb-4216-84ac-d6246ae5546d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1d9abbd095f2d5be7415ed28a17fb710ff8ab504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583840"
---
# <a name="configure-file-system-permissions-for-database-engine-access"></a><span data-ttu-id="978df-102">Configurar permissões do sistema de arquivos para acesso ao mecanismo de banco de dados</span><span class="sxs-lookup"><span data-stu-id="978df-102">Configure File System Permissions for Database Engine Access</span></span>
  <span data-ttu-id="978df-103">Este tópico descreve como conceder ao [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]acesso ao sistema de arquivos ao local onde os arquivos de banco de dados são armazenados.</span><span class="sxs-lookup"><span data-stu-id="978df-103">This topic describes how to grant the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], file system access to the location where database files are stored.</span></span> <span data-ttu-id="978df-104">O serviço do [!INCLUDE[ssDE](../../includes/ssde-md.md)] deve ter a permissão do sistema de arquivos do Windows para acessar a pasta onde os arquivos de banco de dados são armazenados.</span><span class="sxs-lookup"><span data-stu-id="978df-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] service must have permission of the Windows file system to access the file folder where database files are stored.</span></span> <span data-ttu-id="978df-105">A permissão para o local padrão é configurada durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="978df-105">Permission to the default location is configured during setup.</span></span> <span data-ttu-id="978df-106">Se você colocar seus arquivos de banco de dados em um local diferente, poderá precisar seguir estas etapas para conceder ao [!INCLUDE[ssDE](../../includes/ssde-md.md)] a permissão de controle total para esse local.</span><span class="sxs-lookup"><span data-stu-id="978df-106">If you place your database files in a different location, you might need to follow these steps to grant the [!INCLUDE[ssDE](../../includes/ssde-md.md)] the full control permission to that location.</span></span>  
  
 <span data-ttu-id="978df-107">A partir do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , as permissões são atribuídas ao SID por serviço para cada um de seus serviços.</span><span class="sxs-lookup"><span data-stu-id="978df-107">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permissions are assigned to the per-service SID for each of its services.</span></span> <span data-ttu-id="978df-108">Este sistema ajuda a fornecer o isolamento de serviço e defesa mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="978df-108">This system helps provide service isolation and defense in depth.</span></span> <span data-ttu-id="978df-109">O SID por serviço é derivado do nome do serviço e é exclusivo a cada serviço.</span><span class="sxs-lookup"><span data-stu-id="978df-109">The per-service SID is derived from the service name and is unique to each service.</span></span> <span data-ttu-id="978df-110">O tópico [Configurar contas de serviço e permissões do Windows](configure-windows-service-accounts-and-permissions.md) descreve o SID por serviço e fornece os nomes na seção **Privilégios e direitos do Windows**.</span><span class="sxs-lookup"><span data-stu-id="978df-110">The topic [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md) describes the per-service SID and provides the names in the section **Windows Privileges and Rights**.</span></span> <span data-ttu-id="978df-111">É o SID por serviço que deve receber a permissão de acesso no local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="978df-111">It is the per-service SID that must be assigned the access permission on the file location.</span></span>  
  
## <a name="to-grant-file-system-permission-to-the-per-service-sid"></a><span data-ttu-id="978df-112">Para conceder permissão do sistema de arquivos ao SID por serviço</span><span class="sxs-lookup"><span data-stu-id="978df-112">To Grant File System Permission to the Per-service SID</span></span>  
  
1.  <span data-ttu-id="978df-113">Usando o Windows Explorer, navegue até o local do sistema de arquivos onde os arquivos de banco de dados são armazenados.</span><span class="sxs-lookup"><span data-stu-id="978df-113">Using Windows Explorer, navigate to the file system location where the database files are stored.</span></span> <span data-ttu-id="978df-114">Clique com o botão direito do mouse na pasta do sistema de arquivos e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="978df-114">Right-click the file system folder, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="978df-115">Na guia **Segurança** , clique em **Editar**e em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="978df-115">On the **Security** tab, click **Edit**, and then **Add**.</span></span>  
  
3.  <span data-ttu-id="978df-116">Na caixa de diálogo **Selecionar Usuários, Computadores, Conta de Serviço ou Grupos** , clique em **Localizações**na parte superior da lista de localizações, selecione o nome de seu computador e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="978df-116">In the **Select Users, Computer, Service Account, or Groups** dialog box, click **Locations**, at the top of the location list, select your computer name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="978df-117">Na caixa **Inserir os nomes de objeto a serem selecionados** , digite o nome do SID por serviço listado no tópico nos Manuais Online **Configurar contas de serviço e permissões do Windows**.</span><span class="sxs-lookup"><span data-stu-id="978df-117">In the **Enter the object names to select** box, type the name of the per-service SID listed in the Books Online topic **Configure Windows Service Accounts and Permissions**.</span></span> <span data-ttu-id="978df-118">(Para o [!INCLUDE[ssDE](../../includes/ssde-md.md)] SID por serviço, use **NT SERVICE\MSSQLSERVER** para uma instância padrão ou **NT Service\MSSQL $ InstanceName** para uma instância nomeada.)</span><span class="sxs-lookup"><span data-stu-id="978df-118">(For the [!INCLUDE[ssDE](../../includes/ssde-md.md)] per service SID, use **NT SERVICE\MSSQLSERVER** for a default instance, or **NT SERVICE\MSSQL$InstanceName** for a named instance.)</span></span>  
  
5.  <span data-ttu-id="978df-119">Clique em **Verificar Nomes** para validar a entrada.</span><span class="sxs-lookup"><span data-stu-id="978df-119">Click **Check Names** to validate the entry.</span></span> <span data-ttu-id="978df-120">A validação geralmente falha e pode alertá-lo de que o nome não foi localizado.</span><span class="sxs-lookup"><span data-stu-id="978df-120">The validation often fails, and might advise you that the name was not found.</span></span> <span data-ttu-id="978df-121">Quando você clica em **OK**, uma caixa de diálogo **Vários nomes encontrados** é exibida.</span><span class="sxs-lookup"><span data-stu-id="978df-121">When you click **OK**, a **Multiple Names Found** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="978df-122">Agora, selecione o SID por serviço, **MSSQLSERVER** ou **NT Service\MSSQL $ InstanceName**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="978df-122">Now select the per-service SID, either **MSSQLSERVER** or **NT SERVICE\MSSQL$InstanceName**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="978df-123">Clique em **OK** novamente para retornar à caixa de diálogo **permissões** .</span><span class="sxs-lookup"><span data-stu-id="978df-123">Click **OK** again to return to the **Permissions** dialog box.</span></span>  
  
8.  <span data-ttu-id="978df-124">Na caixa nomes de **grupo ou de usuário** , selecione o SID por serviço e, na caixa **permissões para** \<name> , marque a caixa de seleção **permitir** para **controle total**.</span><span class="sxs-lookup"><span data-stu-id="978df-124">In the **Group or user** names box, select the per-service SID, and then in the **Permissions for** \<name> box, select the **Allow** check box for **Full control**.</span></span>  
  
9. <span data-ttu-id="978df-125">Clique em **Aplicar**e em **OK** duas vezes para sair.</span><span class="sxs-lookup"><span data-stu-id="978df-125">Click **Apply**, and then click **OK** twice to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="978df-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="978df-126">See Also</span></span>  
 <span data-ttu-id="978df-127">[Gerenciar os serviços do Mecanismo de Banco de Dados](manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="978df-127">[Manage the Database Engine Services](manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="978df-128">[Mover bancos de dados do sistema](../../relational-databases/databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="978df-128">[Move System Databases](../../relational-databases/databases/system-databases.md) </span></span>  
 [<span data-ttu-id="978df-129">Mover bancos de dados de usuário</span><span class="sxs-lookup"><span data-stu-id="978df-129">Move User Databases</span></span>](../../relational-databases/databases/move-user-databases.md)  
  
  
