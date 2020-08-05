---
title: Arquivos de log de rastreamento padrão desabilitados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: c27761e6-75ed-4ee4-a236-0cbc42e500a1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0fed8fb006427b4dda9d99c57cbabca8538efcad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572009"
---
# <a name="default-trace-log-files-disabled"></a><span data-ttu-id="ace01-102">Arquivos de log de rastreamento padrão desabilitados</span><span class="sxs-lookup"><span data-stu-id="ace01-102">Default Trace Log Files Disabled</span></span>
  <span data-ttu-id="ace01-103">Esta regra verifica os valores da opção habilitada sp_configure de rastreamento padrão do procedimento armazenado para determinar se o rastreamento padrão está definido como ON (1) ou OFF (0).</span><span class="sxs-lookup"><span data-stu-id="ace01-103">This rule checks the value of the sp_configure stored procedure default trace enabled option to determine whether default trace is set ON (1) or OFF (0).</span></span> <span data-ttu-id="ace01-104">Quando esta opção está habilitada, o rastreamento padrão fornece informações sobre as alterações na configuração e no DDL do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ace01-104">When this option is enabled, default tracing provides information about configuration and DDL changes to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="ace01-105">Em alguns casos, estas informações podem ser úteis para os clientes, o Atendimento ao consumidor e o Suporte do [!INCLUDE[msCoName](../../includes/msconame-md.md)] quando estiverem solucionando questões sobre o [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ace01-105">In some cases, this information can be helpful for customers and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support when they troubleshooting issues with the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="ace01-106">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="ace01-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="ace01-107">Use o procedimento armazenado sp_configure para habilitar o rastreamento definindo o valor habilitado de rastreamento padrão como 1.</span><span class="sxs-lookup"><span data-stu-id="ace01-107">Use the sp_configure stored procedure to enable tracing by setting the value of default trace enabled to 1.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="ace01-108">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="ace01-108">For More Information</span></span>  
 [<span data-ttu-id="ace01-109">Opções de configuração do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ace01-109">Server Configuration Options &#40;SQL Server&#41;</span></span>](../../database-engine/configure-windows/server-configuration-options-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ace01-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ace01-110">See Also</span></span>  
 [<span data-ttu-id="ace01-111">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="ace01-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
