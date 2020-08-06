---
title: Opção de configuração de servidor c2 audit mode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], C2 Audit Mode option
- C2 auditing
- C2 Audit Mode option
- recording attempts
ms.assetid: 5a8d73a6-c4f6-4967-ba11-ecbcfc90b9cc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3407a2a94a43adb2d3d3b52994093d6ed0c2e684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684899"
---
# <a name="c2-audit-mode-server-configuration-option"></a><span data-ttu-id="5b855-102">Opção c2 audit mode de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="5b855-102">c2 audit mode Server Configuration Option</span></span>
  <span data-ttu-id="5b855-103">O modo de auditoria C2 pode ser configurado pelo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou com a opção **modo de auditoria c2** no **sp_configure**.</span><span class="sxs-lookup"><span data-stu-id="5b855-103">C2 audit mode can be configured through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or with the **c2 audit mode** option in **sp_configure**.</span></span> <span data-ttu-id="5b855-104">Selecionar esta opção configurará o servidor para registrar tentativas com falha e com êxito ao acessar instruções e objetos.</span><span class="sxs-lookup"><span data-stu-id="5b855-104">Selecting this option will configure the server to record both failed and successful attempts to access statements and objects.</span></span> <span data-ttu-id="5b855-105">Essas informações podem ajudá-lo a determinar o perfil da atividade do sistema e rastrear possíveis violações na política de segurança.</span><span class="sxs-lookup"><span data-stu-id="5b855-105">This information can help you profile system activity and track possible security policy violations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="5b855-106">O padrão de segurança C2 foi substituído pela Certificação de Critérios Comuns.</span><span class="sxs-lookup"><span data-stu-id="5b855-106">The C2 security standard has been superseded by Common Criteria Certification.</span></span> <span data-ttu-id="5b855-107">Consulte [Opção de configuração de servidor com conformidade de critérios comuns habilitada](common-criteria-compliance-enabled-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="5b855-107">See the [common criteria compliance enabled Server Configuration Option](common-criteria-compliance-enabled-server-configuration-option.md).</span></span>  
  
## <a name="audit-log-file"></a><span data-ttu-id="5b855-108">Arquivo de auditoria de log</span><span class="sxs-lookup"><span data-stu-id="5b855-108">Audit Log File</span></span>  
 <span data-ttu-id="5b855-109">Os dados do modo de auditoria C2 são salvados no diretório de dados padrão da instância.</span><span class="sxs-lookup"><span data-stu-id="5b855-109">C2 audit mode data is saved in a file in the default data directory of the instance.</span></span> <span data-ttu-id="5b855-110">Se o arquivo de log de auditoria atingir seu limite de tamanho de 200 MB, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] criará um novo arquivo, fechará o arquivo antigo e gravará todos os novos registros de auditoria no novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="5b855-110">If the audit log file reaches its size limit of 200 megabytes (MB), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will create a new file, close the old file, and write all new audit records to the new file.</span></span> <span data-ttu-id="5b855-111">Esse processo continuará até que o diretório de dados de auditoria atinja seu limite ou a auditoria seja desativada.</span><span class="sxs-lookup"><span data-stu-id="5b855-111">This process will continue until the audit data directory fills up or auditing is turned off.</span></span> <span data-ttu-id="5b855-112">Para determinar o estado de um rastreamento de C2, consulte a exibição do catálogo sys.traces.</span><span class="sxs-lookup"><span data-stu-id="5b855-112">To determine the status of a C2 trace, query the sys.traces catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5b855-113">O modo de auditoria C2 salva uma grande quantidade de informações de eventos no arquivo de log, que pode aumentar rapidamente.</span><span class="sxs-lookup"><span data-stu-id="5b855-113">C2 audit mode saves a large amount of event information to the log file, which can grow quickly.</span></span> <span data-ttu-id="5b855-114">Se o diretório de dados no qual os logs estão sendo salvos atingir seu limite de espaço, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será encerrado.</span><span class="sxs-lookup"><span data-stu-id="5b855-114">If the data directory in which logs are being saved runs out of space, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will shut itself down.</span></span> <span data-ttu-id="5b855-115">Se a auditoria for definida para iniciar automaticamente, você deverá reiniciar a instância com o sinalizador **-f** (que passa pela auditoria) ou liberar espaço em disco adicional para o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5b855-115">If auditing is set to start automatically, you must either restart the instance with the **-f** flag (which bypasses auditing), or free up additional disk space for the audit log.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="5b855-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="5b855-116">Permissions</span></span>  
 <span data-ttu-id="5b855-117">Exige associação à função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="5b855-117">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b855-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5b855-118">Example</span></span>  
 <span data-ttu-id="5b855-119">O exemplo a seguir ativa o modo de auditoria C2.</span><span class="sxs-lookup"><span data-stu-id="5b855-119">The following example turns on C2 audit mode.</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
sp_configure 'c2 audit mode', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b855-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5b855-120">See Also</span></span>  
 <span data-ttu-id="5b855-121">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b855-121">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="5b855-122">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5b855-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="5b855-123">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5b855-123">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
