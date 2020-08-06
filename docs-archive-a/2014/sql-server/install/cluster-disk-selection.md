---
title: Seleção de disco de cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster disk selection
ms.assetid: 0d6b863d-5972-4a20-9990-64ee8016fea6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0f53d6d3f623254d2b17996be7fd5b8235dca223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573509"
---
# <a name="cluster-disk-selection"></a><span data-ttu-id="70369-102">Seleção de Disco de Cluster</span><span class="sxs-lookup"><span data-stu-id="70369-102">Cluster Disk Selection</span></span>
  <span data-ttu-id="70369-103">Use a página **Seleção de Disco de Cluster** do Assistente de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a fim de selecionar o recurso de disco de cluster compartilhado do cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70369-103">Use the **Cluster Disk Selection** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to select the shared cluster disk resource for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span> <span data-ttu-id="70369-104">O disco de cluster é o local onde os dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são colocados.</span><span class="sxs-lookup"><span data-stu-id="70369-104">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="70369-105">Um disco de cluster compartilhado não é um requisito para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] instalações de cluster.</span><span class="sxs-lookup"><span data-stu-id="70369-105">A shared cluster disk is not a requirement for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] cluster installations.</span></span> <span data-ttu-id="70369-106">Um servidor de arquivos SMB é um armazenamento com suporte para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] instalações de cluster de failover e pode ser especificado usando a página **mecanismo de banco de dados-data diretórios** antes de concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="70369-106">An SMB file server is a supported storage for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] failover cluster installations, and can be specified by using the **Database Engine - Data Directories** page before completing the installation.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="70369-107">Se você selecionou Analysis Services para ser instalado, especifique um disco de cluster compartilhado.</span><span class="sxs-lookup"><span data-stu-id="70369-107">If you have selected Analysis Services to be installed, you must specify a shared cluster disk.</span></span>  
>   
>  <span data-ttu-id="70369-108">Se você pretende habilitar FILESTREAM nesta instância de cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , especifique um disco de cluster compartilhado.</span><span class="sxs-lookup"><span data-stu-id="70369-108">If you plan to enable FILESTREAM on this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance, you must specify a shared cluster disk.</span></span>  
  
## <a name="options"></a><span data-ttu-id="70369-109">Opções</span><span class="sxs-lookup"><span data-stu-id="70369-109">Options</span></span>  
 <span data-ttu-id="70369-110">**Discos compartilhados**</span><span class="sxs-lookup"><span data-stu-id="70369-110">**Shared Disks**</span></span>  
 <span data-ttu-id="70369-111">Selecione um único disco na lista.</span><span class="sxs-lookup"><span data-stu-id="70369-111">Select a single disk from the list.</span></span> <span data-ttu-id="70369-112">O disco de cluster é o local onde os dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são colocados.</span><span class="sxs-lookup"><span data-stu-id="70369-112">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="70369-113">Apenas um disco pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="70369-113">Only one disk can be specified.</span></span> <span data-ttu-id="70369-114">Se você selecionar o grupo que contém o recurso de quorum de cluster, será exibido um aviso.</span><span class="sxs-lookup"><span data-stu-id="70369-114">If you select the group containing the cluster quorum resource, a warning will be displayed.</span></span> <span data-ttu-id="70369-115">É recomendável não efetuar a instalação no recurso de quorum de cluster.</span><span class="sxs-lookup"><span data-stu-id="70369-115">We recommend that you do not install to the cluster quorum resource.</span></span>  
  
 <span data-ttu-id="70369-116">**Discos compartilhados disponíveis**</span><span class="sxs-lookup"><span data-stu-id="70369-116">**Available Shared Disks**</span></span>  
 <span data-ttu-id="70369-117">Exibe uma lista de discos disponíveis, onde cada um deles é qualificado como um disco compartilhado, e uma descrição de cada recurso de disco.</span><span class="sxs-lookup"><span data-stu-id="70369-117">Displays a list of available disks, whether each is qualified as a shared disk, and a description of each disk resource.</span></span>  
  
  
