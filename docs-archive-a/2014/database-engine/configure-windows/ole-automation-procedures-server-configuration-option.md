---
title: Opção de configuração de servidor Ole Automation Procedures | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Ole Automation Procedures option
ms.assetid: e8982e05-4984-4406-9760-285e8c028ddf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d34615ce1f808c1015c9c3d312a38a67dba291b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678957"
---
# <a name="ole-automation-procedures-server-configuration-option"></a><span data-ttu-id="28807-102">Opção de configuração de servidor Ole Automation Procedures</span><span class="sxs-lookup"><span data-stu-id="28807-102">Ole Automation Procedures Server Configuration Option</span></span>
  <span data-ttu-id="28807-103">Use a opção `Ole Automation Procedures` para especificar se podem ser instanciados objetos de automação OLE dentro de lotes [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28807-103">Use the `Ole Automation Procedures` option to specify whether OLE Automation objects can be instantiated within [!INCLUDE[tsql](../../includes/tsql-md.md)] batches.</span></span> <span data-ttu-id="28807-104">Essa opção também pode ser configurada com o Gerenciamento Baseado em Políticas ou o procedimento armazenado **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="28807-104">This option can also be configured using the Policy-Based Management or the **sp_configure** stored procedure.</span></span> <span data-ttu-id="28807-105">Para obter mais informações, consulte [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="28807-105">For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span></span>  
  
 <span data-ttu-id="28807-106">A opção `Ole Automation Procedures` pode ser definida com os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="28807-106">The `Ole Automation Procedures` option can be set to the following values.</span></span>  
  
 <span data-ttu-id="28807-107">0</span><span class="sxs-lookup"><span data-stu-id="28807-107">0</span></span>  
 <span data-ttu-id="28807-108">Os procedimentos de automação OLE estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="28807-108">OLE Automation Procedures are disabled.</span></span> <span data-ttu-id="28807-109">Padrão para novas instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28807-109">Default for new instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="28807-110">1</span><span class="sxs-lookup"><span data-stu-id="28807-110">1</span></span>  
 <span data-ttu-id="28807-111">Os procedimentos de automação OLE estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="28807-111">OLE Automation Procedures are enabled.</span></span>  
  
 <span data-ttu-id="28807-112">Quando os Procedimentos da Automação OLE forem habilitados, uma chamada a **sp_OACreate** fará com que se inicie o ambiente OLE de execução compartilhado.</span><span class="sxs-lookup"><span data-stu-id="28807-112">When OLE Automation Procedures are enabled, a call to **sp_OACreate** will start the OLE shared execution environment.</span></span>  
  
 <span data-ttu-id="28807-113">O valor atual da `Ole Automation Procedures` opção pode ser exibido e alterado usando o procedimento armazenado do sistema **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="28807-113">The current value of the `Ole Automation Procedures` option can be viewed and changed by using the **sp_configure** system stored procedure.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="28807-114">Exemplos</span><span class="sxs-lookup"><span data-stu-id="28807-114">Examples</span></span>  
 <span data-ttu-id="28807-115">O exemplo a seguir mostra como exibir a configuração atual dos procedimentos de automação OLE.</span><span class="sxs-lookup"><span data-stu-id="28807-115">The following example shows how to view the current setting of OLE Automation procedures.</span></span>  
  
```  
EXEC sp_configure 'Ole Automation Procedures';  
GO  
```  
  
 <span data-ttu-id="28807-116">O exemplo a seguir mostra como habilitar os procedimentos de automação OLE.</span><span class="sxs-lookup"><span data-stu-id="28807-116">The following example shows how to enable OLE Automation procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Ole Automation Procedures', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="28807-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="28807-117">See Also</span></span>  
 <span data-ttu-id="28807-118">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28807-118">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="28807-119">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28807-119">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="28807-120">[Configuração da Área de Superfície](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="28807-120">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 [<span data-ttu-id="28807-121">Opções de configuração do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28807-121">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
