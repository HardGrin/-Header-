using System.Collections;
using System.Collections.Generic;
using System.Threading.Tasks;
using UnityEngine;
using UnityEngine.UI;
using YG;

public class ViborSkin : MonoBehaviour
{
    public InfoYG infYG;
    public List<Image> Buttons = new List<Image>();
    public void ChooseSkin(int SID)
    {
        StaticHolder.skinID = SID;
        Debug.Log("Статих холдер скин равен: " + StaticHolder.skinID);
    }
    public void ColorSkin(int CID)
    {
        StaticHolder.ColorSkin = CID;
    }

    public void ArmySkin(int ARID)
    {
        StaticHolder.ArmySkin = ARID;
    }

    public /*async*/ void TryShowFullscreenAd(GameObject button)
    {

        Debug.Log("показываем рекламу в VibosSkin");
        YandexGame.RewVideoShow(0);///вызваем метод открытия рекламы с вознаграждением
        Destroy(button);
    }
    public void ButtonsColor(int ButtonID)
    {
        Buttons[ButtonID].color = Color.green;
        for (int i = 0; i < Buttons.Count; i++)
        {
            if(i != ButtonID)
            {
                Buttons[i].color = Color.white;
            }
        }
    }

}

// trail.colorGradient.colorKeys
