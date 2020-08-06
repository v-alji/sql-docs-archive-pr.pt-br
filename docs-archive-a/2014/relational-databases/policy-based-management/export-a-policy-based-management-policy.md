---
title: Exportar uma política do Gerenciamento Baseado em Políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, export policy
ms.assetid: f0001b33-9078-4432-8460-496736fb325a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 15f554aeeebfd47c3fa1ea13b100fbe6bcfcc055
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574671"
---
# <a name="export-a-policy-based-management-policy"></a><span data-ttu-id="14e94-102">Exportar uma política do Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="14e94-102">Export a Policy-Based Management Policy</span></span>
  <span data-ttu-id="14e94-103">Este tópico descreve como exportar uma Política de Gerenciamento Baseado em Políticas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14e94-103">This topic describes how to export a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="14e94-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="14e94-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="14e94-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="14e94-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="14e94-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="14e94-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="14e94-107">**Para exportar uma política, usando:**</span><span class="sxs-lookup"><span data-stu-id="14e94-107">**To export a policy, using:**</span></span>  
  
     [<span data-ttu-id="14e94-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="14e94-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="14e94-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="14e94-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="14e94-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="14e94-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="14e94-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="14e94-111">Permissions</span></span>  
 <span data-ttu-id="14e94-112">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="14e94-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="14e94-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="14e94-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-export-a-policy"></a><span data-ttu-id="14e94-114">Para exportar uma política</span><span class="sxs-lookup"><span data-stu-id="14e94-114">To export a policy</span></span>  
  
1.  <span data-ttu-id="14e94-115">No Pesquisador de Objetos, clique no sinal de adição para expandir o servidor que contém a Política de Gerenciamento Baseado em Políticas que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="14e94-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to export.</span></span>  
  
2.  <span data-ttu-id="14e94-116">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="14e94-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="14e94-117">Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.</span><span class="sxs-lookup"><span data-stu-id="14e94-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="14e94-118">Clique no sinal de adição para expandir a pasta **Políticas** .</span><span class="sxs-lookup"><span data-stu-id="14e94-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="14e94-119">Clique com o botão direito do mouse na política a ser exportada e selecione **Exportar Política**.</span><span class="sxs-lookup"><span data-stu-id="14e94-119">Right-click the policy that you want to export and select **Export Policy**.</span></span>  
  
6.  <span data-ttu-id="14e94-120">Na caixa de diálogo **Exportar Política** , digite o caminho e o nome do arquivo na barra de endereços.</span><span class="sxs-lookup"><span data-stu-id="14e94-120">In the **Export Policy** dialog box, type the path and name of the file in the address bar.</span></span> <span data-ttu-id="14e94-121">Como alternativa, encontra o local apropriado para o arquivo no painel de navegação na caixa de diálogo e digite o nome do arquivo XML na caixa **Nome do Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="14e94-121">Alternately, find a suitable location for the file in the dialog box's navigation pane, and then type the name of the XML file in the **File Name** box.</span></span>  
  
7.  <span data-ttu-id="14e94-122">Ao terminar, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="14e94-122">When finished, click **Save**.</span></span>  
  
  
