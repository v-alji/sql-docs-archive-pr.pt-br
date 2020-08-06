---
title: Configurar um banco de dados espelho criptografado | Microsoft Docs
ms.custom: ''
ms.date: 06/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], database mirroring
- encryption [SQL Server], database mirroring
- database master key [SQL Server], database mirroring
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 7329a575-be29-46e0-abc6-1344db37920c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a5148411792f1ea881bba59e599252284575bbdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681139"
---
# <a name="set-up-an-encrypted-mirror-database"></a><span data-ttu-id="d441a-102">Configurar um banco de dados espelho criptografado</span><span class="sxs-lookup"><span data-stu-id="d441a-102">Set Up an Encrypted Mirror Database</span></span>

<span data-ttu-id="d441a-103">Para habilitar a descriptografia automática da chave mestra do banco de dados de um banco de dados espelho, forneça a senha usada para criptografar a chave mestra para a instância de servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="d441a-103">To enable automatic decryption of the database master key of a mirror database, you must provide the password used to encrypt the master key to the mirror server instance.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="d441a-104">e versões posteriores incluem mecanismos para transferir a senha.</span><span class="sxs-lookup"><span data-stu-id="d441a-104">and later versions include mechanisms to transfer the password.</span></span> <span data-ttu-id="d441a-105">Use **sp_control_dbmasterkey_password** para criar uma credencial para a chave mestra de banco de dados antes de você iniciar o espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d441a-105">Use **sp_control_dbmasterkey_password** to create a credential for the database master key before you start database mirroring.</span></span> <span data-ttu-id="d441a-106">Você deve repetir este processo para todos os bancos de dados que serão espelhados.</span><span class="sxs-lookup"><span data-stu-id="d441a-106">You must repeat this process for every database that will be mirrored.</span></span> <span data-ttu-id="d441a-107">Para obter mais informações, veja [sp_control_dbmasterkey_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d441a-107">For more information, see [sp_control_dbmasterkey_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql).</span></span>
  
> [!CAUTION]  
>  <span data-ttu-id="d441a-108">Não habilite a descriptografia de failover de um banco de dados que deve permanecer inacessível a **sa** e outros principais de servidor altamente privilegiados.</span><span class="sxs-lookup"><span data-stu-id="d441a-108">Do not enable failover decryption of a database that must remain inaccessible to **sa** and other highly privileged server principals.</span></span> <span data-ttu-id="d441a-109">É possível configurar um banco de dados de forma que sua hierarquia fundamental não possa ser descriptografada pela chave mestra de serviço.</span><span class="sxs-lookup"><span data-stu-id="d441a-109">You can configure a database so that its key hierarchy cannot be decrypted by the service master key.</span></span> <span data-ttu-id="d441a-110">Essa opção tem suporte como defesa para bancos de dados que contêm informações que não deveria ser acessíveis a **sa** ou outros principais de servidor altamente privilegiados.</span><span class="sxs-lookup"><span data-stu-id="d441a-110">This option is supported as a defense-in-depth for databases that contain information that should not be accessible to **sa** or other highly privileged server principals.</span></span> <span data-ttu-id="d441a-111">Se você habilitar a descriptografia de failover desse banco de dados, removerá essa defesa, permitindo que **sa** e outros principais de servidor altamente privilegiados descriptografem o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d441a-111">Enabling failover decryption of such a database removes this defense-in-depth, enabling **sa** and other highly privileged server principals to decrypt the database.</span></span>  


<!-- Note: We cannot append '?view=sql-server-2016' to these, even tho in theory we might want to. -->

## <a name="see-also"></a><span data-ttu-id="d441a-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d441a-112">See Also</span></span>

[<span data-ttu-id="d441a-113">sp_control_dbmasterkey_password &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d441a-113">sp_control_dbmasterkey_password &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql)

[<span data-ttu-id="d441a-114">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d441a-114">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)

[<span data-ttu-id="d441a-115">ALTER MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d441a-115">ALTER MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-master-key-transact-sql)

[<span data-ttu-id="d441a-116">Hierarquia de criptografia</span><span class="sxs-lookup"><span data-stu-id="d441a-116">Encryption Hierarchy</span></span>](../../relational-databases/security/encryption/encryption-hierarchy.md)

[<span data-ttu-id="d441a-117">Configurando o espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d441a-117">Setting Up Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)

