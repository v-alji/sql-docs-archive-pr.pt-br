---
title: Opção de configuração de servidor common criteria compliance enabled | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- common criteria compliance
helpviewer_keywords:
- CC (common criteria) [Database Engine]
- common criteria compliance [Database Engine]
- Risidual Information Protection [Database Engine]
- RIP (Residual Information Protection)
ms.assetid: 61766eea-c450-408d-af33-fbe7ef8c9ff2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6722d05351b8b9e80240abb4edef0633a97b6da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569656"
---
# <a name="common-criteria-compliance-enabled-server-configuration-option"></a><span data-ttu-id="4b021-102">Opção de configuração de servidor com conformidade de critérios comuns habilitada</span><span class="sxs-lookup"><span data-stu-id="4b021-102">common criteria compliance enabled Server Configuration Option</span></span>
  <span data-ttu-id="4b021-103">A opção conformidade de critérios comuns habilitada habilita os seguintes elementos necessários para os critérios comuns.</span><span class="sxs-lookup"><span data-stu-id="4b021-103">The common criteria compliance enabled option enables the following elements that are required for the Common Criteria.</span></span>  
  
|<span data-ttu-id="4b021-104">Critérios</span><span class="sxs-lookup"><span data-stu-id="4b021-104">Criteria</span></span>|<span data-ttu-id="4b021-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="4b021-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="4b021-106">Proteção de Informação Residual (RIP)</span><span class="sxs-lookup"><span data-stu-id="4b021-106">Residual Information Protection (RIP)</span></span>|<span data-ttu-id="4b021-107">O RIP requer alocação de memória para ser substituído por um padrão conhecido de bits antes que a memória seja realocada para um novo recurso.</span><span class="sxs-lookup"><span data-stu-id="4b021-107">RIP requires a memory allocation to be overwritten with a known pattern of bits before memory is reallocated to a new resource.</span></span> <span data-ttu-id="4b021-108">Atender ao padrão RIP pode contribuir para melhorar a segurança; entretanto, a substituição da alocação de memória pode diminuir o desempenho.</span><span class="sxs-lookup"><span data-stu-id="4b021-108">Meeting the RIP standard can contribute to improved security; however, overwriting the memory allocation can slow performance.</span></span> <span data-ttu-id="4b021-109">Depois que a opção conformidade de critérios comuns habilitada estiver habilitada, ocorre a substituição.</span><span class="sxs-lookup"><span data-stu-id="4b021-109">After the common criteria compliance enabled option is enabled, the overwriting occurs.</span></span>|  
|<span data-ttu-id="4b021-110">A habilidade para exibir estatísticas de logon</span><span class="sxs-lookup"><span data-stu-id="4b021-110">The ability to view login statistics</span></span>|<span data-ttu-id="4b021-111">Depois que a opção conformidade de critérios comuns habilitada é ativada, a auditoria de logon é habilitada.</span><span class="sxs-lookup"><span data-stu-id="4b021-111">After the common criteria compliance enabled option is enabled, login auditing is enabled.</span></span> <span data-ttu-id="4b021-112">Sempre que um usuário fizer um logon bem-sucedido no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], as informações sobre a hora do último logon com êxito e do último logon sem êxito e o número de tentativas entre o último logon bem-sucedido e o logon atual são disponibilizadas.</span><span class="sxs-lookup"><span data-stu-id="4b021-112">Each time a user successfully logs in to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], information about the last successful login time, the last unsuccessful login time, and the number of attempts between the last successful and current login times is made available.</span></span> <span data-ttu-id="4b021-113">Essas estatísticas de logon podem ser exibidas com uma consulta à exibição de gerenciamento dinâmico [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4b021-113">These login statistics can be viewed by querying the [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) dynamic management view.</span></span>|  
|<span data-ttu-id="4b021-114">A coluna GRANT não deve substituir a tabela DENY</span><span class="sxs-lookup"><span data-stu-id="4b021-114">That column GRANT should not override table DENY</span></span>|<span data-ttu-id="4b021-115">Depois que a opção conformidade de critérios comuns habilitada é habilitada, um nível de tabela DENY precede um nível de coluna GRANT.</span><span class="sxs-lookup"><span data-stu-id="4b021-115">After the common criteria compliance enabled option is enabled, a table-level DENY takes precedence over a column-level GRANT.</span></span> <span data-ttu-id="4b021-116">Quando a opção não é habilitada, um nível de coluna GRANT precede um nível de tabela DENY.</span><span class="sxs-lookup"><span data-stu-id="4b021-116">When the option is not enabled, a column-level GRANT takes precedence over a table-level DENY.</span></span>|  
  
 <span data-ttu-id="4b021-117">A opção habilitada para a conformidade de critérios comuns é uma opção avançada.</span><span class="sxs-lookup"><span data-stu-id="4b021-117">The common criteria compliance enabled option is an advanced option.</span></span> <span data-ttu-id="4b021-118">Os critérios comuns somente são avaliados e certificados para as edições Enterprise e Datacenter.</span><span class="sxs-lookup"><span data-stu-id="4b021-118">Common criteria is only evaluated and certified for the Enterprise edition and Datacenter edition.</span></span> <span data-ttu-id="4b021-119">Para obter o status mais recente da certificação de critérios comuns, consulte o site da Web [Microsoft SQL Server Common Criteria (Critérios comuns do Microsoft SQL Server)](https://go.microsoft.com/fwlink/?LinkId=616319) .</span><span class="sxs-lookup"><span data-stu-id="4b021-119">For the latest status of common criteria certification, see the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4b021-120">Além de habilitar a opção common criteria compliance enabled, também é necessário baixar e executar um script que conclui a configuração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para conformidade com o EAL4+ (nível de garantia de avaliação 4+) de Critérios Comuns.</span><span class="sxs-lookup"><span data-stu-id="4b021-120">In addition to enabling the common criteria compliance enabled option, you also must download and run a script that finishes configuring [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to comply with Common Criteria Evaluation Assurance Level 4+ (EAL4+).</span></span> <span data-ttu-id="4b021-121">Você pode fazer download deste script no site [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) .</span><span class="sxs-lookup"><span data-stu-id="4b021-121">You can download this script from the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
 <span data-ttu-id="4b021-122">Se você estiver usando o procedimento armazenado do sistema sp_configure para alterar a definição, poderá alterar a opção conformidade de critérios comuns habilitada somente quando a opção mostrar opções avançadas estiver definida como 1.</span><span class="sxs-lookup"><span data-stu-id="4b021-122">If you are using the sp_configure system stored procedure to change the setting, you can change common criteria compliance enabled only when show advanced options is set to 1.</span></span> <span data-ttu-id="4b021-123">A configuração terá efeito depois que o servidor for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="4b021-123">The setting takes effect after the server is restarted.</span></span> <span data-ttu-id="4b021-124">Os valores possíveis são 0 e 1:</span><span class="sxs-lookup"><span data-stu-id="4b021-124">The possible values are 0 and 1:</span></span>  
  
-   <span data-ttu-id="4b021-125">0 indica que a conformidade dos critérios comuns não está habilitada.</span><span class="sxs-lookup"><span data-stu-id="4b021-125">0 indicates that common criteria compliance is not enabled.</span></span> <span data-ttu-id="4b021-126">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="4b021-126">This is the default.</span></span>  
  
-   <span data-ttu-id="4b021-127">1 indica que a conformidade dos critérios comuns está habilitada.</span><span class="sxs-lookup"><span data-stu-id="4b021-127">1 indicates that common criteria compliance is enabled.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4b021-128">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4b021-128">Examples</span></span>  
 <span data-ttu-id="4b021-129">O exemplo a seguir habilita a conformidade dos critérios comuns.</span><span class="sxs-lookup"><span data-stu-id="4b021-129">The following example enables common criteria compliance.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'common criteria compliance enabled', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b021-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4b021-130">See Also</span></span>  
 [<span data-ttu-id="4b021-131">Opções de configuração do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4b021-131">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
