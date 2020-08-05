---
title: Alterar o endereço IP de uma instância do cluster de failover | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- modifying IP addresses
- failover clustering [SQL Server], IP addresses
- IP addresses [SQL Server]
- clusters [SQL Server], IP addresses
ms.assetid: b685f400-cbfe-4c5d-a070-227a1123dae4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45d3ef0b70282efd870e4a076663719c2549deaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573577"
---
# <a name="change-the-ip-address-of-a-failover-cluster-instance"></a><span data-ttu-id="f320b-102">Alterar o endereço IP de uma instância do cluster de failover</span><span class="sxs-lookup"><span data-stu-id="f320b-102">Change the IP Address of a Failover Cluster Instance</span></span>
  <span data-ttu-id="f320b-103">Este tópico descreve como alterar o recurso de endereço IP em uma FCI (instância de cluster de failover) AlwaysOn usando o snap-in Gerenciador de Cluster de Failover.</span><span class="sxs-lookup"><span data-stu-id="f320b-103">This topic describes how to change the IP address resource in an AlwaysOn Failover Cluster Instance (FCI) by using the Failover Cluster Manager snap-in.</span></span> <span data-ttu-id="f320b-104">O snap-in Gerenciador de Cluster de Failover é o aplicativo de gerenciamento de cluster do serviço WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="f320b-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Server Failover Clustering (WSFC) service.</span></span>  
  
-   <span data-ttu-id="f320b-105">**Antes de começar:**  [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="f320b-105">**Before you begin:**  [Security](#Security)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f320b-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f320b-106">Before You Begin</span></span>  
 <span data-ttu-id="f320b-107">Antes de começar, examine o seguinte tópico dos Manuais Online do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] : [Antes de instalar o Clustering de Failover](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="f320b-107">Before you begin, review the following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online topic: [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f320b-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="f320b-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f320b-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="f320b-109">Permissions</span></span>  
 <span data-ttu-id="f320b-110">Para manter ou atualizar uma FCI, você deve ser um administrador local com permissão para fazer logon como um serviço em todos os nós da FCI.</span><span class="sxs-lookup"><span data-stu-id="f320b-110">To maintain or update an FCI, you must be a local administrator with permission to logon as a service on all nodes of the FCI.</span></span>  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="f320b-111">Usando o snap-in Gerenciador de Cluster de Failover</span><span class="sxs-lookup"><span data-stu-id="f320b-111">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="f320b-112">**Para alterar o recurso de endereço IP para uma FCI**</span><span class="sxs-lookup"><span data-stu-id="f320b-112">**To change the IP address resource for an FCI**</span></span>  
  
1.  <span data-ttu-id="f320b-113">Abra o snap-in Gerenciador de Cluster de Failover.</span><span class="sxs-lookup"><span data-stu-id="f320b-113">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="f320b-114">Expanda o nó **Serviços e aplicativos** , no painel esquerdo e clique na FCI.</span><span class="sxs-lookup"><span data-stu-id="f320b-114">Expand the **Services and applications** node, in the left pane and click on the FCI.</span></span>  
  
3.  <span data-ttu-id="f320b-115">No painel direito, na categoria **Nome do Servidor** , clique com o botão direito do mouse na Instância do SQL Server e selecione **Propriedades** para abrir a caixa de diálogo **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="f320b-115">On the right pane, under the **Server Name** category, right-click the SQL Server Instance, and select **Properties** option to open the **Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="f320b-116">Na guia **Geral** , altere o recurso de endereço IP.</span><span class="sxs-lookup"><span data-stu-id="f320b-116">On the **General** tab, change the IP address resource.</span></span>  
  
5.  <span data-ttu-id="f320b-117">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f320b-117">Click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="f320b-118">No painel direito, clique com o botão direito do mouse no Endereço IP1 SQL (nome da instância do cluster de failover) e selecione **Colocar Offline**.</span><span class="sxs-lookup"><span data-stu-id="f320b-118">In the right-hand pane, right-click the SQL IP Address1(failover cluster instance name) and select **Take Offline**.</span></span> <span data-ttu-id="f320b-119">Você verá o Endereço IP1 SQL(nome da instância do cluster de failover), o Nome de Rede do SQL(nome da instância do cluster de failover) e o status do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mudarem de Online para Pendente Offline e, depois, para Offline.</span><span class="sxs-lookup"><span data-stu-id="f320b-119">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Online to Offline Pending, and then to Offline.</span></span>  
  
7.  <span data-ttu-id="f320b-120">No painel direito, clique com o botão direito do mouse em [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]e selecione **Colocar Online**.</span><span class="sxs-lookup"><span data-stu-id="f320b-120">In the right-hand pane, right-click [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and then select **Bring Online**.</span></span> <span data-ttu-id="f320b-121">Você verá o Endereço IP1 SQL(nome da instância do cluster de failover), o Nome de Rede do SQL(nome da instância do cluster de failover) e o status do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mudarem de Offline para Pendente Online e, depois, para Online.</span><span class="sxs-lookup"><span data-stu-id="f320b-121">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Offline to Online Pending, and then to Online.</span></span>  
  
8.  <span data-ttu-id="f320b-122">Feche o snap-in Gerenciador de Cluster de Failover.</span><span class="sxs-lookup"><span data-stu-id="f320b-122">Close the Failover Cluster Manager snap-in.</span></span>  
  
  
