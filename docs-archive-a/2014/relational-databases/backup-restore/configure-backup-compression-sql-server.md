---
title: Configurar compactação de backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 430905eb-d218-458c-bd48-aeee6fbb7446
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f70994eb64cb6a50b538fd87f03ce7ea2fafe857
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583664"
---
# <a name="configure-backup-compression-sql-server"></a><span data-ttu-id="5fd46-102">Configurar compactação de backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5fd46-102">Configure Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="5fd46-103">Na instalação, a compactação de backup é desativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="5fd46-103">At installation, backup compression is off by default.</span></span> <span data-ttu-id="5fd46-104">O comportamento padrão da compactação de backup é definido pela opção de configuração em nível de servidor **padrão de compactação de backup** .</span><span class="sxs-lookup"><span data-stu-id="5fd46-104">The default behavior for backup compression is defined by the **backup compression default** Option server-level configuration option.</span></span> <span data-ttu-id="5fd46-105">No entanto, você pode substituir o padrão do nível de servidor ao criar um único backup ou agendar uma série de backups rotineiros.</span><span class="sxs-lookup"><span data-stu-id="5fd46-105">However, you can override the server-level default when creating a single backup or scheduling a series of routine backups.</span></span> <span data-ttu-id="5fd46-106">Para alterar o padrão no nível do servidor, consulte [Exibir ou configurar a opção de configuração de servidor padrão de compactação de backup](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="5fd46-106">To change the server-level default, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
## <a name="override-the-backup-compression-default"></a><span data-ttu-id="5fd46-107">Substituir o padrão de compactação de backup</span><span class="sxs-lookup"><span data-stu-id="5fd46-107">Override the Backup Compression Default</span></span>  
 <span data-ttu-id="5fd46-108">É possível alterar o comportamento de compactação de backup para um backup individual, um trabalho de backup ou uma configuração de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="5fd46-108">You can change the backup compression behavior for an individual backup, backup job, or log shipping configuration.</span></span>  
  
-   **[!INCLUDE[tsql](../../includes/tsql-md.md)]**  
  
     <span data-ttu-id="5fd46-109">Para substituir o padrão de compactação de backup do servidor ao criar um backup, use WITH NO_COMPRESSION ou WITH COMPRESSION na instrução [BACKUP](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5fd46-109">To override the server backup-compression default when creating a backup, use either WITH NO_COMPRESSION or WITH COMPRESSION in you [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
     <span data-ttu-id="5fd46-110">Para uma configuração de envio de logs, é possível controlar o comportamento de compactação de backup de backups de log usando [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5fd46-110">For a log shipping configuration, you can control the backup compression behavior of log backups by using [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql).</span></span>  
  
-   **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
     <span data-ttu-id="5fd46-111">Para obter informações sobre como exibir ou configurar opção de padrão de compactação de backup para uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], veja [Exibir ou configurar a opção de configuração de servidor do padrão de compactação de backup](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="5fd46-111">For information about how to view or configure the backup compression default option for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
     <span data-ttu-id="5fd46-112">Você pode substituir o padrão de compactação de backup do servidor durante a criação de um backup especificando **Compactar backup** ou **Não compactar o backup** em qualquer uma das seguintes caixas de diálogo:</span><span class="sxs-lookup"><span data-stu-id="5fd46-112">You can override the server backup-compression default when creating a backup by specifying **Compress backup** or **Do not compress backup** in any of the following dialog boxes:</span></span>  
  
    -   [<span data-ttu-id="5fd46-113">Backup de Banco de Dados (página Opções)</span><span class="sxs-lookup"><span data-stu-id="5fd46-113">Back Up Database (Options Page)</span></span>](back-up-database-backup-options-page.md)  
  
         <span data-ttu-id="5fd46-114">Ao fazer backup de um banco de dados, é possível controlar a compactação de backup de um backup individual de banco de dados, arquivo ou log.</span><span class="sxs-lookup"><span data-stu-id="5fd46-114">When backing up a database, you can control backup compression for an individual database, file, or log backup.</span></span>  
  
    -   [<span data-ttu-id="5fd46-115">Usar o Assistente de Plano de Manutenção</span><span class="sxs-lookup"><span data-stu-id="5fd46-115">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
         <span data-ttu-id="5fd46-116">O Assistente de Plano de Manutenção permite que você controle a compactação de backup para cada conjunto de backups de banco de dados ou de log, completos ou diferenciais, que você programou.</span><span class="sxs-lookup"><span data-stu-id="5fd46-116">The Maintenance Plan Wizard enables you to control backup compression for each set full or differential database backups or log backups that you schedule.</span></span>  
  
    -   <span data-ttu-id="5fd46-117">[Tarefa de backup de banco de dados](../../integration-services/control-flow/back-up-database-task.md)do SSIS (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="5fd46-117">Integration Services (SSIS) [Back Up Database task](../../integration-services/control-flow/back-up-database-task.md)</span></span>  
  
         <span data-ttu-id="5fd46-118">É possível controlar o comportamento da compactação de backup ao criar um pacote para fazer backup de um único banco de dados ou de vários bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="5fd46-118">You can control the backup compression behavior when creating a package for backing up a single database or multiple databases.</span></span>  
  
    -   [<span data-ttu-id="5fd46-119">Configurações de backup de log de transações do envio de log</span><span class="sxs-lookup"><span data-stu-id="5fd46-119">Log Shipping Transaction Log Backup Settings</span></span>](../databases/log-shipping-transaction-log-backup-settings.md)  
  
         <span data-ttu-id="5fd46-120">Você pode controlar o comportamento da compactação de backup de backups de log.</span><span class="sxs-lookup"><span data-stu-id="5fd46-120">You can control the backup compression behavior of log backups.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="5fd46-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5fd46-121">See Also</span></span>  
 [<span data-ttu-id="5fd46-122">Compactação de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5fd46-122">Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
  
