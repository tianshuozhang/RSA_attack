<div align="center">

# 🔓 RSA_attack

**Lattice-based RSA attacks with partial private-key exposure**
**基于格方法的 RSA 部分私钥泄露攻击**

![SageMath](https://img.shields.io/badge/SageMath-1E90FF?style=flat-square&logo=sagemath&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)
![Topic](https://img.shields.io/badge/Topic-Cryptanalysis-red?style=flat-square)

</div>

---

## 📖 Problem · 题目描述

**English** — A user sends several plaintext messages \(m\) with RSA encryption software. All ciphertexts \(c\) have been intercepted, the public values \(e\) and \(N\) are known, and some information about the private key \(d\) has leaked. The goal is to recover as many plaintexts as possible and then recover the key parameters of the software.

**中文** — 本赛题中用户使用 RSA 加密软件发送多组明文字符串消息 \(m\)，假定所有加密数据 \(c\) 都已经被截获，并且公钥证书中 \(e\) 和 \(N\) 的值均已知，此外还额外已知用户私钥 \(d\) 的部分信息。要求选手尽可能多地破解明文消息，并进一步恢复该加密软件的密钥参数信息。

## 🛠️ Methods · 方法

| Notebook | Attack · 攻击方法 | Idea · 思路 |
| --- | --- | --- |
| `work1.ipynb` – `work3.ipynb` | **Boneh–Durfee** small private exponent · 小私钥攻击 | Solve \(x(A+y)+1 \equiv 0 \pmod e\) with a lattice (Herrmann–May optimisation) for \(d < N^{\delta}\) · 用格求解小根，恢复 \(d\) |
| `work8.ipynb` | **Coppersmith** with known low bits of \(d\) · 已知私钥低位 | Lift \(p\) modulo \(2^{l}\) from the leaked bits, then find the remaining high bits of \(p, q\) via bivariate small roots · 由泄露位恢复 \(p\) 的低位，再用 Coppersmith 求高位 |

## 📁 Structure · 目录结构

```text
RSA_attack
├── code/
│   ├── boneh_durfee.sage                       # Boneh–Durfee lattice attack
│   ├── coppersmith.sage                        # multivariate small roots
│   ├── coppersmith_howgrave_univariate.sage    # Howgrave-Graham univariate
│   └── work*.ipynb                             # per-challenge solutions
└── data/                                       # challenge data
```

## 🚀 Usage · 使用方法

```bash
# requires SageMath with a Jupyter kernel
cd code
sage -n jupyter
```

Open a `work*.ipynb` notebook and run all cells. 打开对应的 `work*.ipynb` 依次运行即可。
