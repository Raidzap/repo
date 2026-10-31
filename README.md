# Raidzap Repo

Fonte APT para Sileo e Zebra com os tweaks do Raidzap para iOS com jailbreak rootless.

**Adicionar a fonte:** `https://raidzap.github.io/repo/`

Serve jailbreaks rootless (`iphoneos-arm64`) e rootful (`iphoneos-arm`); o Sileo e o Zebra mostram só os pacotes da arquitetura do aparelho.

No Sileo: **Fontes → + → Adicionar fonte**. Ou abra o endereço no Safari do iPhone e toque em **Adicionar ao Sileo** / **Adicionar ao Zebra**. As dependências vêm dos repositórios do bootstrap (Procursus).

| Pacote | Projeto |
| --- | --- |
| `dev.manual7.camera` | [Manual7](https://github.com/Raidzap/Manual7) |

## Publicar um pacote

```sh
python3 build_repo.py . /caminho/para/pacote.deb
git add -A && git commit -m "Add pacote X.Y.Z" && git push
```

O pacote é copiado para `debs/`, e `Packages`, `Release` e `index.html` são gerados de novo a partir de todos os `.deb` dessa pasta. Para tirar uma versão do ar, apague o `.deb` de `debs/` e rode `python3 build_repo.py .` sem argumentos. O GitHub Pages publica o branch `main`.
