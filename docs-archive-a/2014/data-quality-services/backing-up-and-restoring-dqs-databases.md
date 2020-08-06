---
title: Fazendo backup e restaurando bancos de dados do DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f3091f62-2234-4a80-a615-cf14c2a1da85
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 489664d8c64a99d1ea4dcec79b93e5b01b28f649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570275"
---
# <a name="backing-up-and-restoring-dqs-databases"></a><span data-ttu-id="cd249-102">Fazendo backup e restaurando banco de dados do DQS</span><span class="sxs-lookup"><span data-stu-id="cd249-102">Backing Up and Restoring DQS Databases</span></span>
  <span data-ttu-id="cd249-103">Este tópico descreve como fazer backup e restaurar os bancos de dados do DQS.</span><span class="sxs-lookup"><span data-stu-id="cd249-103">This topic describes how to back up and restore the DQS databases.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cd249-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="cd249-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="cd249-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="cd249-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="cd249-106">Você deve saber ou se lembrar da senha da chave mestra do banco de dados que forneceu durante a instalação do servidor DQS.</span><span class="sxs-lookup"><span data-stu-id="cd249-106">You must know or remember the password for the database master key that you provided during the DQS server installation.</span></span>  
  
-   <span data-ttu-id="cd249-107">Verifique se não há nenhuma atividade ou processo em execução no DQS.</span><span class="sxs-lookup"><span data-stu-id="cd249-107">Ensure that there are no running activities or processes in DQS.</span></span> <span data-ttu-id="cd249-108">Isso pode ser verificado com o uso da tela **Monitoramento de atividade** .</span><span class="sxs-lookup"><span data-stu-id="cd249-108">This can be verified using the **Activity Monitoring** screen.</span></span> <span data-ttu-id="cd249-109">Para obter informações detalhadas sobre como trabalhar nessa tela, consulte [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span><span class="sxs-lookup"><span data-stu-id="cd249-109">For detailed information about working in this screen, see [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span></span>  
  
-   <span data-ttu-id="cd249-110">Verifique se não há usuários conectados no servidor DQS.</span><span class="sxs-lookup"><span data-stu-id="cd249-110">Ensure that there are no users logged on the DQS server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cd249-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="cd249-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cd249-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="cd249-112">Permissions</span></span>  
  
-   <span data-ttu-id="cd249-113">Sua conta de usuário do Windows deve ser um membro da função de servidor fixa sysadmin na instância do SQL Server para executar as operações de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="cd249-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance to perform the backup and restore operations.</span></span>  
  
-   <span data-ttu-id="cd249-114">Você deve ter a função dqs_administrator no banco de dados DQS_MAIN para terminar as atividades em execução ou interromper os processos em execução no DQS.</span><span class="sxs-lookup"><span data-stu-id="cd249-114">You must have the dqs_administrator role on the DQS_MAIN database to terminate any running activities or stop any running processes in DQS.</span></span>  
  
##  <a name="backup-and-restore-dqs-databases"></a><a name="BackupRestore"></a><span data-ttu-id="cd249-115">Fazer backup e restaurar bancos de dados do DQS</span><span class="sxs-lookup"><span data-stu-id="cd249-115">Backup and Restore DQS Databases</span></span>  
  
1.  <span data-ttu-id="cd249-116">Inicie o Microsoft SQL Server Management Studio e conecte-se à instância apropriada do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cd249-116">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="cd249-117">No Pesquisador de Objetos, expanda o nó **Bancos de Dados** .</span><span class="sxs-lookup"><span data-stu-id="cd249-117">In Object Explorer, expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="cd249-118">Faça um backup do banco de dados DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="cd249-118">Back up the DQS_STAGING_DATA database.</span></span> <span data-ttu-id="cd249-119">Para obter instruções passo a passo de como fazer backup de um banco de dados do SQL Server, consulte [Criar um backup completo de banco de dados &#40;SQL Server&#41;](../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cd249-119">For step-by-step instructions for backing a SQL Server database, see [Create a Full Database Backup &#40;SQL Server&#41;](../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="cd249-120">Faça backup do banco de dados DQS_PROJECTS.</span><span class="sxs-lookup"><span data-stu-id="cd249-120">Back up the DQS_PROJECTS database.</span></span>  
  
5.  <span data-ttu-id="cd249-121">Faça backup do banco de dados DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="cd249-121">Back up the DQS_MAIN database.</span></span>  
  
6.  <span data-ttu-id="cd249-122">Desconecte-se da instância atual do SQL Server e conecte-se à instância do SQL Server em que você deseja restaurar esses bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="cd249-122">Disconnect from the current instance of SQL Server, and connect to the SQL Server instance where you want to restore these databases.</span></span>  
  
7.  <span data-ttu-id="cd249-123">Restaure o banco de dados DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="cd249-123">Restore DQS_MAIN database.</span></span> <span data-ttu-id="cd249-124">Para obter instruções detalhadas sobre como restaurar um banco de dados SQL Server, consulte [restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="cd249-124">For step-by-step instructions to restore a SQL Server database, see [Restore a Database Backup &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md).</span></span>  
  
8.  <span data-ttu-id="cd249-125">Restaure o banco de dados DQS_PROJECTS.</span><span class="sxs-lookup"><span data-stu-id="cd249-125">Restore the DQS_PROJECTS database.</span></span>  
  
9. <span data-ttu-id="cd249-126">Restaure o banco de dados DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="cd249-126">Restore the DQS_STAGING_DATA database.</span></span>  
  
10. <span data-ttu-id="cd249-127">No Pesquisador de Objetos, clique com o botão direito do mouse no servidor e, depois, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="cd249-127">In Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
11. <span data-ttu-id="cd249-128">Na janela Editor de consultas, copie as seguintes instruções SQL e substitua *\<PASSWORD>* pela senha que você forneceu durante a instalação do DQS para a chave mestra do banco de dados:</span><span class="sxs-lookup"><span data-stu-id="cd249-128">In the Query Editor window, copy the following SQL statements, and replace *\<PASSWORD>* with the password that you provided during the DQS installation for the database master key:</span></span>  
  
    ```sql  
    USE [DQS_MAIN]  
    GO  
    EXECUTE [internal_core].[RestoreDQDatabases] '<PASSWORD>'  
    GO  
    ```  
  
12. <span data-ttu-id="cd249-129">Pressione F5 para executar as instruções.</span><span class="sxs-lookup"><span data-stu-id="cd249-129">Press F5 to execute the statements.</span></span> <span data-ttu-id="cd249-130">Consulte o painel **Resultados** para verificar se as instruções foram executadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="cd249-130">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd249-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cd249-131">See Also</span></span>  
 [<span data-ttu-id="cd249-132">Gerenciar bancos de dados do DQS</span><span class="sxs-lookup"><span data-stu-id="cd249-132">Manage DQS Databases</span></span>](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
