---
title: Novidades na instalação do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- installing SQL Server, what's new
- SQL Server, what's new
- SQL Server, installing
ms.assetid: c8642a96-3a09-4ec7-a9c3-c539147e6330
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d34085e320cd8ca0b82d382d6d49eaa303086114
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573392"
---
# <a name="what39s-new-in-sql-server-installation"></a><span data-ttu-id="0ac2b-102">Novidades na instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="0ac2b-102">What&#39;s New in SQL Server Installation</span></span>
  <span data-ttu-id="0ac2b-103">O Windows Vista não é um sistema operacional com suporte para o [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ac2b-103">Windows Vista is not a supported operating system for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span> <span data-ttu-id="0ac2b-104">O Service Pack 1 permanece como o requisito mínimo para sistemas operacionais [!INCLUDE[win7](../../includes/win7-md.md)] e [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ac2b-104">Service Pack 1 remains as the minimum requirement for [!INCLUDE[win7](../../includes/win7-md.md)] and [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] operating systems.</span></span> <span data-ttu-id="0ac2b-105">Para obter mais informações sobre os requisitos do sistema operacional, consulte [requisitos de hardware e software para a instalação do SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0ac2b-105">For more information on operating system requirements, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
 <span data-ttu-id="0ac2b-106">A instalação do [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] solicitará que você especifique o diretório para salvar o pacote extraído.</span><span class="sxs-lookup"><span data-stu-id="0ac2b-106">Installation of [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] will prompt you to specify the directory to save the extracted package.</span></span> <span data-ttu-id="0ac2b-107">Se nenhum local for inserido, o [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] usará como padrão a unidade do sistema do computador.</span><span class="sxs-lookup"><span data-stu-id="0ac2b-107">If no location is entered, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] will default to the computer's system drive.</span></span> <span data-ttu-id="0ac2b-108">Os arquivos extraídos permanecerão depois que a instalação do [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] estiver concluída.</span><span class="sxs-lookup"><span data-stu-id="0ac2b-108">The extracted files will remain after [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] installation is complete.</span></span>  
  
 <span data-ttu-id="0ac2b-109">No [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], o SysPrep tem suporte para todas as instalações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ac2b-109">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], SysPrep is supported for all installations of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0ac2b-110">O SysPrep agora dá suporte a instalações de cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="0ac2b-110">SysPrep now supports failover cluster installations.</span></span> <span data-ttu-id="0ac2b-111">Para obter mais informações, consulte [considerações para instalar SQL Server usando o Sysprep](../../database-engine/install-windows/considerations-for-installing-sql-server-using-sysprep.md) e [instalar SQL Server 2014 usando o Sysprep](../../database-engine/install-windows/install-sql-server-using-sysprep.md).</span><span class="sxs-lookup"><span data-stu-id="0ac2b-111">For more information, see [Considerations for Installing SQL Server Using SysPrep](../../database-engine/install-windows/considerations-for-installing-sql-server-using-sysprep.md) and [Install SQL Server 2014 Using SysPrep](../../database-engine/install-windows/install-sql-server-using-sysprep.md).</span></span>  
  
 <span data-ttu-id="0ac2b-112">A atualização do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] tem suporte, mas lado a lado não.</span><span class="sxs-lookup"><span data-stu-id="0ac2b-112">Upgrade from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] is supported, but side-by-side is not supported.</span></span> <span data-ttu-id="0ac2b-113">Para obter mais informações sobre o suporte de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] no [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], consulte [Atualizações de versão e edição com suporte](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="0ac2b-113">For more information about [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] support in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], see [Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span></span>  
  
 <span data-ttu-id="0ac2b-114">A partir do [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], o mecanismo de banco de dados na edição Standard tem uma capacidade de memória de 128 GB.</span><span class="sxs-lookup"><span data-stu-id="0ac2b-114">Beginning in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], the database engine in the Standard edition has a memory capacity of 128 GB.</span></span> <span data-ttu-id="0ac2b-115">No [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , o mecanismo de banco de dados na Standard Edition tinha uma capacidade de memória de 64 GB.</span><span class="sxs-lookup"><span data-stu-id="0ac2b-115">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the database engine in the Standard edition had a memory capacity of 64 GB.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac2b-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ac2b-116">See Also</span></span>  
 <span data-ttu-id="0ac2b-117">[O que há de novo no SQL Server 2014](../what-s-new-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="0ac2b-117">[What's New in SQL Server 2014](../what-s-new-in-sql-server-2016.md) </span></span>  
 <span data-ttu-id="0ac2b-118">[Especificações do produto para o SQL Server 2014](../../../2014/getting-started/sql-server-2014-product-specifications.md) </span><span class="sxs-lookup"><span data-stu-id="0ac2b-118">[Product Specifications for SQL Server 2014](../../../2014/getting-started/sql-server-2014-product-specifications.md) </span></span>  
 <span data-ttu-id="0ac2b-119">[Planejando uma instalação do SQL Server](../../../2014/sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="0ac2b-119">[Planning a SQL Server Installation](../../../2014/sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="0ac2b-120">Requisitos de hardware e software para instalação do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0ac2b-120">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
  
