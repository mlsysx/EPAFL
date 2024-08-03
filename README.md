# Efficient Privacy Attacks in Federated Learning (EPAFL)
Code for the paper [On the Efficiency of Privacy Attacks in Federated Learning](https://arxiv.org/abs/2404.09430)

# Privacy Attack
There are significant privacy risks in Federated Learning e.g. Gradient Leakage Attack where the attacker aims to reconstruct data from shared gradients. Each device computes local gradients and sends them to the server. The attacker/server uses an optimization algorithm to reconstruct gradients that would result in original data.

![](https://github.com/mlsysx/EPAFL/blob/main/assets/attack-visualization.jpg)

# Overview of EPAFL
The attack algorithms mainly focus on improving success rates and often ignore the computational overhead of recovering private data which limits their practical applicability. We emphasize efficiency in privacy attacks and evaluate computational costs of gradient leakage attacks. Our proposed EPAFL can substantially decrease reconstruction cost while maintaining comparable attack effectiveness.

![](https://github.com/mlsysx/EPAFL/blob/main/assets/EPAFL.jpg)

The efficiency of privacy attacks can be greatly enhanced by applying early-stopping techniques.

```python
#detectplateau
if best_val_loss is None or current_loss < best_val_loss:
    best_val_loss = current_loss
    wait = 0

    # Threshold
    if current_loss < threshold:
        print('Iteration required: ', iters + 1)
        train_iters = iters + 1
        early_stop = True
        break  # converge

elif wait >= patience:
    print('Iteration required: ', iters + 1)
    train_iters = iters + 1
    early_stop = True
    break  # converge

else:
    wait += 1

```
 
# Citing
If you find this work useful in your research, please cite the following paper:

```bibtex
@INPROCEEDINGS{epafl,
    author={Tabassum, Nawrin and Chow, Ka-Ho and Wang, Xuyu and Zhang, Wenbin and Wu, Yanzhao},
    booktitle={2024 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR) Workshops}, 
    title={On the Efficiency of Privacy Attacks in Federated Learning}, 
    year={2024},
    pages={4226-4235}
}
