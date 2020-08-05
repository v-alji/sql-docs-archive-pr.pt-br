---
title: Inicialização imediata de arquivo do banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- initializing files [SQL Server]
- instant file initializations [SQL Server]
- fast file initialization (SQL Server)
- file initialization [SQL Server]
ms.assetid: 1ad468f5-4f75-480b-aac6-0b01b048bd67
author: stevestein
ms.author: sstein
ms.openlocfilehash: dedd2c5b8d075dee8aeeb438904137558c664d95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573108"
---
# <a name="database-instant-file-initialization"></a><span data-ttu-id="849ec-102">Inicialização imediata de arquivo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="849ec-102">Database Instant File Initialization</span></span>
  <span data-ttu-id="849ec-103">Arquivos de dados e de log são inicializados para substituir todos os dados existentes que foram deixados no disco por arquivos excluídos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="849ec-103">Data and log files are initialized to overwrite any existing data left on the disk from previously deleted files.</span></span> <span data-ttu-id="849ec-104">Primeiro, os arquivos de dados e de log são inicializados ao serem completados com zeros quando você executa uma das seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="849ec-104">Data and log files are first initialized by filling the files with zeros when you perform one of the following operations:</span></span>  
  
-   <span data-ttu-id="849ec-105">Criar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="849ec-105">Create a database.</span></span>  
  
-   <span data-ttu-id="849ec-106">Adicionar arquivos, log ou dados a um banco de dados existente.</span><span class="sxs-lookup"><span data-stu-id="849ec-106">Add files, log or data, to an existing database.</span></span>  
  
-   <span data-ttu-id="849ec-107">Aumentar o tamanho de um arquivo existente (inclusive operações de aumento automático).</span><span class="sxs-lookup"><span data-stu-id="849ec-107">Increase the size of an existing file (including autogrow operations).</span></span>  
  
-   <span data-ttu-id="849ec-108">Restaurar um banco de dados ou grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="849ec-108">Restore a database or filegroup.</span></span>  
  
 <span data-ttu-id="849ec-109">A inicialização dos arquivos faz com que essas operações demorem mais.</span><span class="sxs-lookup"><span data-stu-id="849ec-109">File initialization causes these operations to take longer.</span></span> <span data-ttu-id="849ec-110">Porém, quando os dados são gravados nos arquivos pela primeira vez, o sistema operacional não precisa completar os arquivos com zeros.</span><span class="sxs-lookup"><span data-stu-id="849ec-110">However, when data is written to the files for the first time, the operating system does not have to fill the files with zeros.</span></span>  
  
## <a name="instant-file-initialization"></a><span data-ttu-id="849ec-111">Inicialização imediata de arquivo</span><span class="sxs-lookup"><span data-stu-id="849ec-111">Instant File Initialization</span></span>  
 <span data-ttu-id="849ec-112">Em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], os arquivos de dados podem ser inicializados de imediato.</span><span class="sxs-lookup"><span data-stu-id="849ec-112">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data files can be initialized instantaneously.</span></span> <span data-ttu-id="849ec-113">Isso permite execução rápida das operações de arquivo mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="849ec-113">This allows for fast execution of the previously mentioned file operations.</span></span> <span data-ttu-id="849ec-114">A inicialização imediata de um arquivo recupera espaço em disco sem encher esse espaço com zeros.</span><span class="sxs-lookup"><span data-stu-id="849ec-114">Instant file initialization reclaims used disk space without filling that space with zeros.</span></span> <span data-ttu-id="849ec-115">Em vez disso, o conteúdo do disco é substituído à medida que novos dados são gravados nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="849ec-115">Instead, disk content is overwritten as new data is written to the files.</span></span> <span data-ttu-id="849ec-116">Arquivos de log não podem ser inicializados de imediato.</span><span class="sxs-lookup"><span data-stu-id="849ec-116">Log files cannot be initialized instantaneously.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="849ec-117">A Inicialização Instantânea de Arquivo está disponível apenas no [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] ou [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] ou em versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="849ec-117">Instant file initialization is available only on [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] or [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="849ec-118">A inicialização imediata de arquivos estará disponível somente se a conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) tiver recebido SE_MANAGE_VOLUME_NAME.</span><span class="sxs-lookup"><span data-stu-id="849ec-118">Instant file initialization is only available if the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) service account has been granted SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="849ec-119">Os membros do grupo administrador do Windows têm esse direito e podem atribuí-lo a outros usuários adicionando-os à política de segurança **Executar tarefas de manutenção de volume** .</span><span class="sxs-lookup"><span data-stu-id="849ec-119">Members of the Windows Administrator group have this right and can grant it to other users by adding them to the **Perform Volume Maintenance Tasks** security policy.</span></span> <span data-ttu-id="849ec-120">Para obter mais informações sobre como atribuir direitos de usuário, consulte a documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="849ec-120">For more information about assigning user rights, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="849ec-121">A inicialização instantânea de arquivo não está disponível quando a TDE está habilitada.</span><span class="sxs-lookup"><span data-stu-id="849ec-121">Instant file initialization is not available when TDE is enabled.</span></span>  
  
 <span data-ttu-id="849ec-122">Para conceder a permissão `Perform volume maintenance tasks` a uma conta:</span><span class="sxs-lookup"><span data-stu-id="849ec-122">To grant an account the `Perform volume maintenance tasks` permission:</span></span>  
  
1.  <span data-ttu-id="849ec-123">No computador em que o arquivo de backup será criado, abra o aplicativo `Local Security Policy` (`secpol.msc`).</span><span class="sxs-lookup"><span data-stu-id="849ec-123">On the computer where the backup file will be created, open the `Local Security Policy` application (`secpol.msc`).</span></span>  
  
2.  <span data-ttu-id="849ec-124">No painel esquerdo, expanda **Políticas Locais**e, em seguida, clique em **Atribuição de Direitos de Usuário**.</span><span class="sxs-lookup"><span data-stu-id="849ec-124">In the left pane, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
3.  <span data-ttu-id="849ec-125">No painel direito, clique duas vezes em **Executar tarefas de manutenção de volume**.</span><span class="sxs-lookup"><span data-stu-id="849ec-125">In the right pane, double-click **Perform volume maintenance tasks**.</span></span>  
  
4.  <span data-ttu-id="849ec-126">Clique em **Adicionar Usuário ou Grupo** e adicione as contas de usuário que são usadas ​​para backups.</span><span class="sxs-lookup"><span data-stu-id="849ec-126">Click **Add User or Group** and add any user accounts that are used for backups.</span></span>  
  
5.  <span data-ttu-id="849ec-127">Clique em **aplicar**e feche todas as `Local Security Policy` caixas de diálogo.</span><span class="sxs-lookup"><span data-stu-id="849ec-127">Click **Apply**, and then close all `Local Security Policy` dialog boxes.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="849ec-128">Considerações de segurança</span><span class="sxs-lookup"><span data-stu-id="849ec-128">Security Considerations</span></span>  
 <span data-ttu-id="849ec-129">Como o conteúdo excluído do disco é substituído somente à medida que novos dados são gravados nos arquivos, o conteúdo excluído poderá ser acessado por uma entidade de segurança não autorizada.</span><span class="sxs-lookup"><span data-stu-id="849ec-129">Because the deleted disk content is overwritten only as new data is written to the files, the deleted content might be accessed by an unauthorized principal.</span></span> <span data-ttu-id="849ec-130">Embora o arquivo de banco de dados esteja associado à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], essa ameaça de divulgação de informações é reduzida pela lista de controle de acesso discricionário (DACL) no arquivo.</span><span class="sxs-lookup"><span data-stu-id="849ec-130">While the database file is attached to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this information disclosure threat is reduced by the discretionary access control list (DACL) on the file.</span></span> <span data-ttu-id="849ec-131">Essa DACL permite acesso de arquivo somente à conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e ao administrador local.</span><span class="sxs-lookup"><span data-stu-id="849ec-131">This DACL allows file access only to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the local administrator.</span></span> <span data-ttu-id="849ec-132">Porém, quando o arquivo é desassociado, ele pode ser acessado por um usuário ou serviço que não tenha SE_MANAGE_VOLUME_NAME.</span><span class="sxs-lookup"><span data-stu-id="849ec-132">However, when the file is detached, it may be accessed by a user or service that does not have SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="849ec-133">Existe uma ameaça semelhante ao se fazer backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="849ec-133">A similar threat exists when the database is backed up.</span></span> <span data-ttu-id="849ec-134">O conteúdo excluído pode ficar disponível para um usuário ou serviço não autorizado se o arquivo de backup não for protegido com uma DACL adequada.</span><span class="sxs-lookup"><span data-stu-id="849ec-134">The deleted content can become available to an unauthorized user or service if the backup file is not protected with an appropriate DACL.</span></span>  
  
 <span data-ttu-id="849ec-135">Se o potencial de divulgação do conteúdo excluído for uma preocupação, você deve tomar uma ou ambas as providências seguintes:</span><span class="sxs-lookup"><span data-stu-id="849ec-135">If the potential for disclosing deleted content is a concern, you should do one or both of the following:</span></span>  
  
-   <span data-ttu-id="849ec-136">Sempre se certifique de que todos os arquivos de dados desassociados e arquivos de backup tenham DACL restritivas.</span><span class="sxs-lookup"><span data-stu-id="849ec-136">Always make sure that any detached data files and backup files have restrictive DACLs.</span></span>  
  
-   <span data-ttu-id="849ec-137">Desabilite a inicialização de arquivo imediata para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revogando o direito SE_MANAGE_VOLUME_NAME da conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="849ec-137">Disable instant file initialization for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by revoking SE_MANAGE_VOLUME_NAME from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="849ec-138">Desabilitar a inicialização de arquivos imediata afeta somente os arquivos que forem criados ou tiverem seu tamanho aumentado após ser revogado o direito do usuário.</span><span class="sxs-lookup"><span data-stu-id="849ec-138">Disabling instant file initialization only affects files that are created or increased in size after the user right is revoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="849ec-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="849ec-139">See Also</span></span>  
 [<span data-ttu-id="849ec-140">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="849ec-140">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
