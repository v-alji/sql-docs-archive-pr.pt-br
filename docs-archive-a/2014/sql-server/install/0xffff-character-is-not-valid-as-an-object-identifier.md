---
title: o caractere 0xFFFF não é válido como um identificador de objeto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- 0xFFFF character [SQL Server]
ms.assetid: b2c9c8cf-9194-45e0-be6b-2d5ec52e8153
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4594c1cca0fc183100d927842cc2b533694bf90e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573553"
---
# <a name="0xffff-character-is-not-valid-as-an-object-identifier"></a><span data-ttu-id="8717c-102">Caractere 0xFFFF não é válido como um identificador de objeto</span><span class="sxs-lookup"><span data-stu-id="8717c-102">0xFFFF character is not valid as an object identifier</span></span>
  <span data-ttu-id="8717c-103">O Supervisor de Atualização detectou o caractere 0xFFFF em um identificador de objeto.</span><span class="sxs-lookup"><span data-stu-id="8717c-103">Upgrade Advisor has detected the 0xFFFF character in an object identifier.</span></span> <span data-ttu-id="8717c-104">No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e em versões posteriores, objetos como bancos de dados, tabelas e colunas que contêm esse caractere em seus identificadores não podem ser referenciados ou renomeados quando o modo de compatibilidade do banco de dados estiver definido como 90 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="8717c-104">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later, objects such as databases, tables, and columns that contain this character in their identifiers cannot be referenced or renamed when the database compatibility mode is set to 90 or later.</span></span> <span data-ttu-id="8717c-105">Quando você faz a atualização para o [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], os bancos de dados mantêm seus modos de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="8717c-105">When you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], user databases maintain their compatibility mode.</span></span> <span data-ttu-id="8717c-106">Antes de você alterar o modo de compatibilidade do banco de dados para 90 ou posterior, renomeie o objeto que contém o caractere 0xFFFF.</span><span class="sxs-lookup"><span data-stu-id="8717c-106">Before you change the database compatibility mode to 90 or later, rename the object that contains the 0xFFFF character.</span></span>  
  
 <span data-ttu-id="8717c-107">Para obter mais informações sobre os identificadores, consulte ‘Identificadores’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8717c-107">For more information about identifiers, see "Identifiers" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="8717c-108">Para obter mais informações sobre modos de compatibilidade de banco de dados, consulte ‘sp_dbcmptlevel’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8717c-108">For more information about database compatibility modes, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="8717c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="8717c-109">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8717c-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8717c-110">See Also</span></span>  
 <span data-ttu-id="8717c-111">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="8717c-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="8717c-112">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="8717c-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
