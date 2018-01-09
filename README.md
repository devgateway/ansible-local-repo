# devgateway.rpm-gpg

Install RPM GPG public keys from URL or literal.

Role Variables
--------------

## Required

### `gpg_name`

Name of the key. Becomes part of the destination file name, see `repo_gpg_path` and `repo_gpg_prefix`.

### `gpg_key`

Can be a URL or literal key contents, see example below.

## Optional

### `repo_gpg_path`

The directory where RPM GPG keys are stored.

Default: `/etc/pki/rpm-gpg`

### `repo_gpg_prefix`

Prefix given to all key files.

Default: `RPM-GPG-KEY-`

Example Playbook
----------------

    - hosts: all
      tasks:
        - name: Install repo keys
          include_role:
            name: devgateway.rpm-gpg
          vars:
            gpg_name: "{{ item.gpg_name }}"
            gpg_key: "{{ item.gpg_key }}"
          with_items:
            - gpg_name: foo
              gpg_key: https://packages.example.org/foo.key
            - gpg_name: bar
              gpg_key: |
                -----BEGIN PGP PUBLIC KEY BLOCK-----
                
                mQENBE+O/7IBCAC+6ZqjV2GRJ5B3TmdWOOkHbKkcQCWHyYpPxtceRtG9qK3viKc7
                fFT96nN4bSt3zxSrOYncRPIT6NjUA44HjaSM6TaRncGThATSmzN7nxGJq/H0t5qX
                dU4Nic0VVtDa9a29Wg6p9qEcS86De6Ts0B0yLrgXIJ2r6QZm2WMRUHPVniLLN3bG
                szXBkjupG4cQmW9Y+vM6IT4lTTg3kSEAn0sf2m8y5Mlnx5353UXtBpmyCz0rgn9w
                jBJ9U5GPt21OGD6+kDwNAEk5/N3yZtoLQBqPdlBpBKiICfO8z/NTf0bWX556u3JV
                mUvNut6IKh3f5sEx4+QE+25bWZJBvpQT89mTABEBAAG0PFN0eW9wYSBTZW1lbnVr
                aGEgKEFkbWluKSA8c3NlbWVudWtoYUBkZXZlbG9wbWVudGdhdGV3YXkub3JnPokB
                VQQTAQIAPwIbAwYLCQgHAwIGFQgCCQoLBBYCAwECHgECF4AWIQQqA6c93t5D5s/5
                qBXnKyAeuPNsIQUCWQIOEQUJDxao3wAKCRDnKyAeuPNsIV9KB/9DdNcimhZMSz3A
                dg5h5XvlSX6X0bh+0zdUeZFXZBsWNihBP/xJKObEjwItBzwR4ccjWRdDximmC63b
                /Yr+ywgsctHnw8cmbHB/MF/K0r3a8pRSaayBOgrficJUYekDuoUCEuuXJ9jik8A0
                oEpgjUg/8otWOeWfyNc1Jimf1SmN1dj1q7efjMIZb9nGmbgZiEDY8Lkl7qLtC96r
                ikkfuT7r4LTM3dVowQlO2ursCxm7YUvH7KzBrNbCOnA3O8nvVMR/w+f00fJ0Mw7y
                qxuJFnz1mbu6Oa1qoFZDF53fGkJEF6dioHRF2pmKk4A6F2e6cd9hLCUb5v18FDyq
                tzt+HTXRuQENBE+O/7IBCACkwLP6T6VXdkZQIOooaPe+ZuiqBAkNNC+qkkNg5GvQ
                mL7j/wnPIILr1+hKAnZr5Fsc0b5MO0XwLfHEackxPNa5zMXZ0iFjSU1nEGgwUqhM
                i6h9Ule3GM3pHQWkcIzsXqbxt9OAGijEYFyQvtZuYR7DD3AkImw0NAYN3aIm88Oz
                /6ujkJFJMv54DuWOqa2gjSfaRlIt5X9L+IKDXLPzjuK2aF3g+x880PL1nrzUNlSd
                xld7Gw6Y/BeYO39h7Y3RT0paHFsLxo6YngGGLiF0eWvnOsoYVhQR5f9K9hG/cy2q
                Fz5BvaBWwLZwNkThHkl+0erUxFdNF1YoS4maHFRYGimxABEBAAGJATwEGAECACYC
                GwwWIQQqA6c93t5D5s/5qBXnKyAeuPNsIQUCWQIOcQUJDxapPwAKCRDnKyAeuPNs
                IWP4B/49y7BTkR+7grJbgawXwdRYNfjTlI1Eh3YdVd+CUrjuuSOUPuIrUT2+qcsz
                bz2L/l/WU3gtPjEZS1fsaoK6G4scQGW+7MNtvEkIvY36xOL/dedMIJ1mzEmt8lvr
                TQpahnW8oqlo0zT7aOUXqR/L1tSLHPK1q3yM/WQRFOFEifY1QJl4jq7eZbAMkiKA
                yTWx7KnBJ7JtB1LDbWHxfh1i4+8D2RFmWzTgirUwIHtKgWMN+tD30kd5oBaLkwTJ
                v9ogrtskx+p9/1OtXJooZS4AljSmUUblRLGWjKglG+Yl8fR9LoqqZLFwEiIW/OYO
                gtM1b2Ns9isgvj6zGMQKAhYjse57
                =ieb0
                -----END PGP PUBLIC KEY BLOCK-----

License
-------

GPLv3+

Author Information
------------------

Development Gateway
