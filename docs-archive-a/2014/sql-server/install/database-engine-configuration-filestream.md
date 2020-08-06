---
title: Configuração de Mecanismo de Banco de Dados-FileStream | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], about FILESTREAM
ms.assetid: 641a10a1-ae52-4d26-8f1c-a032a4aeff02
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab12b507246a3e13ac59be213813604d531d9a28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683335"
---
# <a name="database-engine-configuration---filestream"></a><span data-ttu-id="79080-102">Configuração do Mecanismo de Banco de Dados – Fluxo de arquivos</span><span class="sxs-lookup"><span data-stu-id="79080-102">Database Engine Configuration - Filestream</span></span>
  <span data-ttu-id="79080-103">Use esta página para habilitar FILESTREAM para esta instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79080-103">Use this page to enable FILESTREAM for this installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="79080-104">O FILESTREAM integra o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] com um sistema de arquivos NTFS armazenando `varbinary(max)` dados BLOB (objeto binário grande) como arquivos no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="79080-104">FILESTREAM integrates the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with an NTFS file system by storing `varbinary(max)` binary large object (BLOB) data as files on the file system.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="79080-105">podem inserir, atualizar, consultar, pesquisar e fazer backup de dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="79080-105">statements can insert, update, query, search, and back up FILESTREAM data.</span></span> <span data-ttu-id="79080-106">As interfaces do sistema de arquivos do Win32 fornecem acesso de streaming aos dados.</span><span class="sxs-lookup"><span data-stu-id="79080-106">Win32 file system interfaces provide streaming access to the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="79080-107">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="79080-107">UI element list</span></span>  
 <span data-ttu-id="79080-108">**Habilitar FILESTREAM para acesso Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="79080-108">**Enable FILESTREAM for Transact-SQL access**</span></span>  
 <span data-ttu-id="79080-109">Selecione para habilitar FILESTREAM para acesso [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79080-109">Select to enable FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="79080-110">Este controle deve ser verificado antes que as demais opções de controle fiquem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="79080-110">This control must be checked before the other control options will be available.</span></span>  
  
 <span data-ttu-id="79080-111">**Habilitar FILESTREAM para acesso de fluxo de E/S de arquivo**</span><span class="sxs-lookup"><span data-stu-id="79080-111">**Enable FILESTREAM for file I/O streaming access**</span></span>  
 <span data-ttu-id="79080-112">Selecione para habilitar o acesso de fluxo Win32 para FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="79080-112">Select to enable Win32 streaming access for FILESTREAM.</span></span>  
  
 <span data-ttu-id="79080-113">**Nome de compartilhamento do Windows**</span><span class="sxs-lookup"><span data-stu-id="79080-113">**Windows share name**</span></span>  
 <span data-ttu-id="79080-114">Use este controle para digitar o nome do compartilhamento do Windows no qual os dados FILESTREAM serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="79080-114">Use this control to enter the name of the Windows share in which the FILESTREAM data will be stored.</span></span>  
  
 <span data-ttu-id="79080-115">**Permitir que clientes remotos tenham acesso de fluxo a dados FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="79080-115">**Allow remote clients to have streaming access to FILESTREAM data**</span></span>  
 <span data-ttu-id="79080-116">Selecione este controle para permitir que clientes remotos acessem dados FILESTREAM neste servidor.</span><span class="sxs-lookup"><span data-stu-id="79080-116">Select this control to allow remote clients to access this FILESTREAM data on this server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79080-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79080-117">See Also</span></span>  
 <span data-ttu-id="79080-118">[Habilitar e configurar FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="79080-118">[Enable and Configure FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="79080-119">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="79080-119">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
